# Use Node.js 9 base image
FROM node:9-slim

RUN npm install -g pnpm

WORKDIR /app

# Install dependencies and build the app
COPY package.json ./
COPY pnpm-lock.yaml ./
RUN pnpm install

COPY . .
# Run the production build (outputs to dist/ by default)
RUN pnpm run build

# Install a simple static file server to serve the built files
RUN npm install -g serve

# Expose port 8081 for the web server
EXPOSE 8080

# Command to serve the built files on port 8081
CMD ["serve", "-s", "dist", "-l", "8080"]
