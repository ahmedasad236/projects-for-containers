# Build Container
FROM node AS build
WORKDIR /app
COPY . .
RUN npm ci && npm run build

# runtime stage
FROM nginx:1.17

COPY --from=build /app/build/ /usr/share/nginx/html