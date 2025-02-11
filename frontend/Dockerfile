# Build Stage
FROM node:20-bullseye-slim AS build
WORKDIR /frontend
COPY package.json yarn.lock ./
RUN yarn install --frozen-lockfile
COPY . .
RUN yarn build

# Serve with Nginx
FROM nginx:latest
COPY  --from=build /frontend/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
