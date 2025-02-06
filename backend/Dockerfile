FROM node:20
WORKDIR /backend
COPY package.json yarn.lock ./
RUN yarn install --production
COPY . .
EXPOSE 5000
CMD ["yarn","start"]