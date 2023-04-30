# Use an official Node.js runtime as a parent image
FROM node:14-alpine

# Set the working directory to /app/backend
WORKDIR /yolo/backend

# Copy the package.json and package-lock.json files to the container
COPY backend/package*.json ./

# Install the dependencies
RUN npm install

# Copy the rest of the application code to the container
COPY backend/ ./

# Expose port 5000 for the backend to listen on
EXPOSE 5000

# Start the backend server
CMD ["npm", "start"]
