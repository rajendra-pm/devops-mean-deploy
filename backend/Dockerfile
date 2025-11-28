FROM node:18-alpine

WORKDIR /app

# copy package.json and lock file if present
COPY package*.json ./

# install production dependencies only
RUN npm install --only=production

# copy source code
COPY . .

EXPOSE 3000
CMD ["node", "server.js"]
