# Front-end Dockerfile

```
FROM node:16-alpine3.16
WORKDIR /home
COPY example-frontend example-frontend
WORKDIR /home/example-frontend
RUN npm install
RUN REACT_APP_BACKEND_URL=http://127.0.0.1:7000 npm run build
RUN npm install -g serve
CMD serve -s -l 5000 build
```

## Command Used

`docker run -p 127.0.0.1:3000:5000 front-end`

# Back-end Dockerfile

```
FROM golang:1.16.15-alpine3.15
WORKDIR /home
COPY example-backend example-backend
WORKDIR /home/example-backend
RUN go build
RUN apk add build-base
RUN go test ./...
ENV PORT=9000
ENV REQUEST_ORIGIN=http://127.0.0.1:3000
CMD ./server
```

## Command Used

`docker run -p 127.0.0.1:7000:9000 back-end`
