
ARG NODE_VERSION=19.7.0


FROM node:${NODE_VERSION}-alpine AS Client
WORKDIR /app/client
COPY ./package.json ./
RUN npm install --force
ENV NODE_ENV production
COPY ./ ./
EXPOSE 3000
CMD ["npm", "start"]
