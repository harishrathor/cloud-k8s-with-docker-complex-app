FROM node:16-alpine as builder
WORKDIR '/app'

COPY package.json /app/
RUN npm install 
COPY . .
RUN npm install

FROM nginx
EXPOSE 3000
COPY ./nginx/defualt.conf /etc/nginx/conf.d/defualt.conf
COPY --from=builder /app/build /usr/share/nginx/html

