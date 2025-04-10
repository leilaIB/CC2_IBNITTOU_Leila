# Etape 1: Build
FROM node:16 AS build

WORKDIR /app
COPY package.json package-lock.json ./
RUN npm install

# Etape 2: Run
FROM node:16
WORKDIR /app
COPY --from=build /app /app
COPY . ./
EXPOSE 3000
CMD ["node", "server.js"]
