# Stage 1

FROM node:alpine as build-step
WORKDIR /app
COPY /app/package.json /app
RUN npm install
COPY . .

RUN npm run build

# Stage 2

FROM nginx:alpine
COPY --from=build-step /app/dist /usr/share/nginx/html
