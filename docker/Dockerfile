# base image
FROM node:16.14-alpine3.15

RUN addgroup -g 1001 speedoc \
  && adduser -u 1001 -G speedoc -s /bin/sh -h /demo -D speedoc \
  && mkdir -p /demo/logs \
  && chown -R speedoc:speedoc /demo

# create & set working directory
WORKDIR /demo

# copy source files
COPY --chown=speedoc:speedoc . /demo

ENV NODE_ENV development
RUN yarn

USER speedoc
# start app
EXPOSE 3000/tcp
ENTRYPOINT [ "yarn", "dev" ]
