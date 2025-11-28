FROM node:20.19.5-alpine3.21 AS builder
WORKDIR /opt/server
COPY package.json .
COPY *.js .
RUN npm install

FROM node:20.19.5-alpine3.21 AS build
WORKDIR /opt/server
COPY --from=builder /opt/server /opt/server
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue"
CMD ["node", "server.js"]








# FROM node:20
# WORKDIR /opt/server
# COPY package.json .
# COPY *.js .
# RUN npm install
# ENV MONGO="true" \
#     MONGO_URL="mongodb://mongodb:27017/catalogue"
# CMD ["node", "server.js"]    