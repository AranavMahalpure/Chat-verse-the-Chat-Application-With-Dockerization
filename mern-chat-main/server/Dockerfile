ARG NODE_VERSION=19.7.0

FROM node:${NODE_VERSION}-alpine AS Backend
WORKDIR /app/server
COPY ./package.json ./
RUN npm install
ENV NODE_ENV production
ENV MONGODB_URI mongodb://host.docker.internal:27000/chat
ENV JWT_SECRET kjsdhfaskdfhl
COPY ./ ./
EXPOSE 5000
CMD ["node", "server.js"]
