# Etape 1: Build
FROM node:16 AS build

WORKDIR /app
COPY package.json package-lock.json ./
RUN npm install
RUN npm run build

# Etape 2: Serve
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
