# Stage 1: Build
FROM node:18-alpine AS builder

# Set working directory
WORKDIR /simple-mern-stack/frontend

# Copy package files and install dependencies
COPY frontend/package*.json ./
RUN npm install

# Copy the source code
COPY frontend/ .

# Build the application
RUN npm run build

# Stage 2: Serve
FROM nginx:alpine

# Copy the build output to the Nginx HTML directory
COPY --from=builder /simple-mern-stack/frontend/dist /usr/share/nginx/html

# Expose port
EXPOSE 80

# Start Nginx server
CMD ["nginx", "-g", "daemon off;"]
