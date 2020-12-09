FROM node:13 as nodebuild
WORKDIR /app
COPY package*.json /app/
RUN npm install -g ionic
RUN npm install
COPY ./ /app/
RUN npm run-script build:prod
FROM nginx:alpine
RUN rm -rf /usr/share/nginx/html/*
COPY --from=nodebuild /app/www/ /usr/share/nginx/html/