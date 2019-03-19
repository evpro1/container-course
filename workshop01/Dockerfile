FROM node:latest

ENV DB_HOST=mydb DB_PORT=3306 DB_USER=root DB_PASSWORD=changeit 
ENV APP_DIR=/app APP_PORT=3000

# all work done inside here
WORKDIR ${APP_DIR}

# ADD statements below
ADD config config
ADD public public
ADD views views

ADD main.js .
ADD package-lock.json .
ADD package.json .

#Install libs
RUN npm install

#Expose port
EXPOSE ${APP_PORT}

#Run application
ENTRYPOINT [ "node","main.js" ]
CMD [ "$APP_PORT" ]