FROM node:18-alpine
WORKDIR /home
RUN apk update && apk add git
RUN git clone https://github.com/Rjnishant530/wordman.git
WORKDIR /home/wordman
RUN npm install
RUN npm run build
RUN npm install -g serve
CMD serve -s -l 5000 build