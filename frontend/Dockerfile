# frontend/Dockerfile
# build stage
FROM node:18-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
# adjust build command if different
RUN npm run build -- --output-path=dist --configuration=production

# production stage
FROM nginx:stable-alpine
COPY --from=builder /app/dist /usr/share/nginx/html
# Remove default nginx.conf and add our own if needed (we'll use separate reverse proxy nginx)
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
