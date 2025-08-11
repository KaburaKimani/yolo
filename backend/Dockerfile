FROM node:16-alpine
WORKDIR /home/liz/yolo
COPY package*.json ./
RUN npm install 
COPY . .

FROM node:18-alpine
WORKDIR /app
COPY --from=builder /app /app
EXPOSE 8000
CMD ["node", "server.js"]

