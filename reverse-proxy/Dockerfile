FROM node as build

WORKDIR /app
# Install app dependencies by copying
# package.json and package-lock.json
COPY package*.json .

RUN npm build

FROM nginx:alpine 

COPY --from=build /app/nginx.conf /etc/nginx/conf.d/default.conf

