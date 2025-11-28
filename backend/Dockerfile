# backend/Dockerfile
FROM node:18-alpine

WORKDIR /app

# copy package files first for caching
COPY package*.json ./

RUN npm ci --only=production

# copy source
COPY . .

# expose port used by backend (change if your app uses other port)
ENV PORT=3000
EXPOSE 3000

# start (expects "start" script in package.json)
CMD ["npm", "start"]
