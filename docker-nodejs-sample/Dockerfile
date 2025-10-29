# ---- Stage 1: Build the app ----
FROM node:18-alpine AS build
WORKDIR /app

# Copy package files and install deps
COPY package*.json ./
RUN npm ci --omit=dev

# Copy the rest of the code
COPY . .

# ---- Stage 2: Run with PM2 ----
FROM node:18-alpine
WORKDIR /app

# Install PM2 globally
RUN npm install -g pm2

# Copy built app from previous stage
COPY --from=build /app /app

EXPOSE 3000

# Use PM2 to start the app
CMD ["pm2-runtime", "server.js"]
