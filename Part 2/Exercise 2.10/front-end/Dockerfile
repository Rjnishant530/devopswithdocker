FROM node:16-alpine3.16
WORKDIR /home
COPY example-frontend example-frontend
WORKDIR /home/example-frontend
RUN npm install
RUN REACT_APP_BACKEND_URL=http://localhost/api npm run build
RUN npm install -g serve
CMD serve -s -l 5000 build