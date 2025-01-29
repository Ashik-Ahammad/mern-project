# Stage 1: Build

FROM node:23.6.1 AS build

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build






# Stage 2: Runtime

FROM nginx:alpine

COPY --from=build /app/build /usr/share/nginx/html

EXPOSE 5173

CMD ["nginx", "-g", "daemon off;"]





