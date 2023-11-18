# FROM node:14.21.3-alpine3.17
# WORKDIR cd /app
# COPY . .
# # ENV MONGO=true
# RUN npm install
# CMD ["node", "server.js"]


FROM node:14.21.3-alpine3.17
EXPOSE 8080
RUN addgroup -S cart && adduser -S cart cart
WORKDIR /opt/server
RUN chown -R cart:cart /opt/server
USER cart
COPY package.json .
COPY server.js .
RUN npm install
CMD ["node", "server.js"]

#this will limit the logged in user to get the root access , giving the high security to the container. This is done by creating the system user
#and make it to run all the operations from COPY package.json