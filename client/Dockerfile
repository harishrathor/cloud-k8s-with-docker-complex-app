FROM node:16-alpine as builder
WORKDIR '/app'

COPY package.json /app/
RUN npm install 
COPY . .
RUN npm run build

FROM nginx
EXPOSE 80
COPY ./nginx/defualt.conf /etc/nginx/conf.d/defualt.conf
COPY --from=builder /app/build /usr/share/nginx/html

