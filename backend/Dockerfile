FROM node:20-bullseye-slim
WORKDIR /app
COPY package.json yarn.lock ./
RUN yarn install --production
COPY . .
EXPOSE 4000
CMD ["yarn","start"]