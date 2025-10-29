# Use official Node.js image as the base
FROM node:18

# Set working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy all source code
COPY . .

# Expose the app port (change if your app uses another one)
EXPOSE 3000

# Command to start the app
CMD ["npm", "start"]
