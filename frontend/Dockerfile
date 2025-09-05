# Stage 1: Build Angular App
FROM node:18 AS build

WORKDIR /app

# Install dependencies
COPY package*.json ./
RUN npm install

# Copy the entire frontend source code
COPY . .

# Build Angular app for production
RUN npm run build -- --configuration production


# Stage 2: Run with Nginx
FROM nginx:alpine

# Copy Angular build files to Nginx html directory
COPY --from=build /app/dist/* /usr/share/nginx/html/

# Optional: Add custom Nginx config if you need API proxying
# COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

