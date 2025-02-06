FROM node:20
WORKDIR /frontend
COPY package.json yarn.lock ./
RUN yarn install --production
COPY . .
RUN yarn run build

# Use Nginx Image to server the frontend
FROM nginx:latest
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx","-g","daemon off;"]

