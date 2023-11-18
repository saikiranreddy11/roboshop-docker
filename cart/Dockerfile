FROM node:14.21.3-alpine3.17
WORKDIR cd /app
COPY . .
# ENV MONGO=true
RUN npm install
CMD ["node", "server.js"]