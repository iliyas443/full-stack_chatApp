# Use official Node.js image
FROM node:18-alpine

# Install build tools for native Node modules
RUN apk add --no-cache python3 g++ make git

# Set working directory
WORKDIR /app

# Copy package files first (cache dependencies)
COPY package.json package-lock.json ./

# Install dependencies
RUN npm ci

# Copy the rest of the app
COPY . .

# Expose port
EXPOSE 3000

# Default start command
CMD ["npm", "start"]
