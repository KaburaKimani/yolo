FROM node:16-alpine
WORKDIR /home/liz/yolo
COPY package*.json ./
RUN npm config set fetch-timeout 600000 && npm config set fetch-retries 5
RUN npm install --omit=dev
COPY . .

FROM node:18-alpine
WORKDIR /app
COPY --from=builder /app /app
EXPOSE 8000
CMD ["node", "server.js"]

