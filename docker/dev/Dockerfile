# base image
FROM node:16.14-alpine3.15 as builder

# create & set working directory
WORKDIR /src
COPY package*.json /src
RUN yarn install
COPY . /src

ENV NODE_ENV development
EXPOSE 3000/tcp
CMD ["yarn", "dev"]
