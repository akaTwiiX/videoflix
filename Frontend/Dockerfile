# Stage 1: Build the Angular application
FROM node:20-alpine AS build

WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the application code
COPY . .

# Build the project using NX
RUN npx nx build videoflix --configuration=production

# Stage 2: Serve the application with Nginx
FROM nginx:alpine

# Copy the custom nginx configuration if exists, otherwise use default
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Copy the build output to Nginx's html directory
COPY --from=build /app/dist/apps/videoflix/browser /usr/share/nginx/html

# Expose port 80
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
