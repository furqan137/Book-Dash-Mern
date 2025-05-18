# Use Node.js base image
FROM node:18-alpine

# Set working directory
WORKDIR /simple-mern-stack/backend

# Copy package files and install dependencies
COPY backend/package*.json ./
RUN npm install

# Copy the source code
COPY backend/ .

# Expose port
EXPOSE 5000

# Start the backend server
CMD ["npm", "start"]
