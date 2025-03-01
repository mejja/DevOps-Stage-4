FROM node:16-alpine

WORKDIR /app

# Copy package files and install dependencies
COPY package.json package-lock.json ./
RUN npm install

# Copy the rest of the application source code
COPY . .

# Expose the application port (adjust if needed)
EXPOSE 8082

# Start the application using node (instead of nodemon for production)
CMD ["node", "server.js"]
