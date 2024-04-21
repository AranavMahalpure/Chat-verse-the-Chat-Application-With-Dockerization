# Use a specific node version for both stages
ARG NODE_VERSION=19.7.0

# First stage: build the backend
FROM node:${NODE_VERSION}-alpine AS Backend
WORKDIR /app/server
COPY ./package.json ./
RUN npm install
ENV NODE_ENV production
ENV MONGODB_URI mongodb://host.docker.internal:27000/chat
ENV JWT_SECRET kjsdhfaskdfhl
COPY ./server/ ./server
EXPOSE 5000
CMD ["node", "server/server.js"]

# Second stage: build the client
FROM node:${NODE_VERSION}-alpine AS Client
WORKDIR /app/client
COPY ./client/package.json ./
RUN npm install --force
ENV NODE_ENV production
COPY ./client ./
EXPOSE 3000
CMD ["npm", "start"]
