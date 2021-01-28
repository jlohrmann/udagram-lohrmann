# Use NodeJS base image
FROM node:13

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies by copying
# package.json and package-lock.json
COPY package*.json ./reverse-proxy

# Install dependencies
RUN npm ci

FROM nginx:alpine 

COPY --from=build /usr/src/app/nginx.conf /etc/nginx/conf.d/default.conf

