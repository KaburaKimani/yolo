FROM node:16-alpine AS builder
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install --production --silent && \
    npm cache clean --force
COPY . .
RUN npm run build

FROM alpine:3.16
WORKDIR /app
RUN apk add --no-cache nodejs
COPY --from=builder /usr/src/app/node_modules ./node_modules
COPY --from=builder /usr/src/app/package*.json ./
COPY --from=builder /usr/src/app/dist ./dist  # Or your compiled files
EXPOSE 5000
CMD ["node", "server.js"]