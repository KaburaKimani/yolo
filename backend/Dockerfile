FROM node:18
WORKDIR /home/liz/yolo
COPY package*.json ./
RUN npm install --production
COPY . .
EXPOSE 3001
CMD ["node", "server.js"]

