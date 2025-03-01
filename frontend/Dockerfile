# Use Node.js to build the frontend
FROM node:12-alpine AS build

WORKDIR /app
COPY package.json package-lock.json ./
RUN npm install
COPY . .

# Expose the port that will serve your app
EXPOSE 8080

# Start Python's simple HTTP server on port 8080
CMD ["npm", "run", "dev"]
