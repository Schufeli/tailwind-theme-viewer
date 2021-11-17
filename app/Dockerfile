# FROM node:alpine as build-step

# RUN mkdir -p /app

# WORKDIR /app
# COPY /app/package.json /app
# RUN npm install

# COPY . /app
# ENV NODE_OPTIONS=--openssl-legacy-provider
# RUN npm run build

# FROM nginx:alpine as deployment-step
# COPY --from=build-step /app/dist /usr/share/nginx/html

# develop stage
FROM node:11.1-alpine as develop-stage
WORKDIR /app
COPY package*.json ./
RUN yarn install
COPY . .

# build stage
FROM develop-stage as build-stage
RUN yarn build# production stage

# production stage
FROM nginx:1.15.7-alpine as production-stage
COPY --from=build-stage /app/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]