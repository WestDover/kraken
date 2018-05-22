FROM node:latest as builder
COPY ./package.json /package.json
COPY ./package-lock.json /package-lock.json
RUN cd / && npm install

FROM nginx:alpine
COPY ./index.html /usr/share/nginx/html/index.html
COPY --from=builder /node_modules/bootstrap/dist/css/bootstrap.min.css /usr/share/nginx/html/bootstrap.css
COPY --from=builder /node_modules/bootstrap/dist/js/bootstrap.min.js /usr/share/nginx/html/bootstrap.js
