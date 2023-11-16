FROM node:14
WORKDIR cd /app
COPY . .
ENV MONGO=true
RUN npm install
CMD ["node", "server.js"]