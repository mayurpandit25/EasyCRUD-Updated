FROM node:24-alpine
COPY . /opt/
WORKDIR /opt
RUN npm install && npm run build
RUN apk update && apk add apache2
RUN rm -rf /var/www/localhost/htdocs/*
RUN cp -rf dist/* /var/www/localhost/htdocs
EXPOSE 80
ENTRYPOINT ["httpd","-D","FOREGROUND"]

##MULTI-STAGE DOCKERFILE##
#stage-1 building stage
#FROM node:24-alpine AS builder
#WORKDIR /app
#COPY . .
#RUN npm install && npm run build

#stage-2 application stage
#FROM httpd:latest
#RUN rm /usr/local/apache2/htdocs/*
#COPY --from=builder /app/dist/ /usr/local/apache2/htdocs/
#EXPOSE 80
#CMD ["httpd","-D","FOREGROUND"]
