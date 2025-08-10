FROM node:18-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm config set fetch-timeout 600000 && npm config set fetch-retries 5
RUN npm install --omit=dev
COPY . .

FROM node:18-alpine
WORKDIR /app
COPY --from=builder /app /app
EXPOSE 8000
CMD ["node", "server.js"]