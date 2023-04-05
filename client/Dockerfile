# Build stage
FROM node:14-alpine as build-stage
WORKDIR /app
COPY package*.json ./
RUN npm install --only=production && npm cache clean --force
RUN npm install react-scripts
COPY . .
RUN npm run build && rm -rf node_modules && npm install --only=production --no-audit && npm cache clean --force

# Production stage
FROM node:14-alpine3.14 as production-stage
WORKDIR /app
COPY --from=build-stage /app/build ./build
COPY package*.json ./
RUN npm install --only=production --no-audit && npm cache clean --force
EXPOSE 3000
CMD ["npm", "start"]