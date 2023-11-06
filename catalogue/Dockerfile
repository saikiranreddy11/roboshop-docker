FROM node:14
WORKDIR cd /app
COPY . .
ENV mongo=true
RUN npm install
CMD ["node", "server.js"]