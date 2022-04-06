# base image
FROM node:16.14-alpine3.15 as builder

# create & set working directory
WORKDIR /demo

# copy source files
COPY . /demo

ENV NODE_ENV development
RUN yarn \
    && yarn build

FROM gcr.io/distroless/nodejs:16

COPY --from=builder /demo /demo

# start app
WORKDIR /demo
ENV NODE_ENV production
EXPOSE 3000/tcp
CMD ["./node_modules/next/dist/bin/next", "start" ]
