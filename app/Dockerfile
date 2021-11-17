FROM node:alpine as build-step

WORKDIR /app
COPY /app/package.json /app
RUN npm install

COPY . /app/
ENV NODE_OPTIONS=--openssl-legacy-provider
RUN npm run build

FROM nginx:alpine as deployment-step
COPY --from=build-step /app/dist /usr/share/nginx/html