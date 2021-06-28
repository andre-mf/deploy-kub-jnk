FROM node:14.16.1-alpine3.13
WORKDIR /app
# COPY package*.json ./
# RUN npm install
RUN ls -la
COPY . .
EXPOSE 8080
CMD ["node", "app.js"]