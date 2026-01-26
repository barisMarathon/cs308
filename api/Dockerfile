FROM node:20-slim

WORKDIR /app

# Install deps first (better layer cache)
COPY package*.json ./
RUN npm ci --omit=dev

# Copy source
COPY . .

# Cloud Run listens on $PORT (default 8080)
ENV PORT=8080
EXPOSE 8080

CMD ["npm","start"]
