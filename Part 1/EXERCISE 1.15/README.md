# Wordman

A Game which displays a color and you have to guess the correct color code.

_Forked from https://github.com/stevekinney/wordman_

# DockerHub

https://hub.docker.com/r/rjnishant530/wordman

# How to use DockerHub Image

The internal port is 5000. No additional arguments needed

To run the docker in your localhost on port 3000 use <br>
`docker run -p 127.0.0.1:3000:5000 rjnishant530/wordman`

# Dockerfile

```
FROM node:18-alpine
WORKDIR /home
RUN apk update && apk add git
RUN git clone https://github.com/Rjnishant530/wordman.git
WORKDIR /home/wordman
RUN npm install
RUN npm run build
RUN npm install -g serve
CMD serve -s -l 5000 build
```
