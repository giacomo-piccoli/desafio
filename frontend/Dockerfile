# Base image
FROM node:14 as build

# Set working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the application files
COPY . .

# Build the Angular app
RUN npm run build -- --prod

# Use nginx as the base image
FROM nginx:1.21.1-alpine

# Copy the built Angular app from the build stage to the nginx public directory
COPY --from=build /app/dist/myapp /usr/share/nginx/html

# Expose port 80
EXPOSE 80

# Start nginx
CMD ["nginx", "-g", "daemon off;"]
