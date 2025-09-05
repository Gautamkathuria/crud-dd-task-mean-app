# Use Node.js base image
FROM node:18

WORKDIR /app

# Install dependencies
COPY package*.json ./
RUN npm install

# Copy backend source code
COPY . .

# Expose the backend port
EXPOSE 5000

# Start the server
CMD ["npm", "start"]

