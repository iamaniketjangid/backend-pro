# Use official Node.js image
FROM node:18

# Set working directory inside container
WORKDIR /app

# Copy package files first (for caching)
COPY package*.json ./

# Install PM2 globally and project dependencies
RUN npm install -g pm2 && npm install

# Copy the rest of the app code
COPY . .

# Expose port 3000 for the app
EXPOSE 3000

# Run the app with PM2 in production mode
CMD ["pm2-runtime", "src/index.js"]
