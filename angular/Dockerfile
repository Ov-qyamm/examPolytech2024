FROM node:10 AS builder

LABEL maintainer="GautierHuver"

WORKDIR /app

COPY . .

RUN npm install 

RUN npm run build --configuration=production

EXPOSE 4200

FROM nginx

COPY nginx/ /etc/nginx/

COPY --from=builder /app/dist/*/* /usr/share/nginx/html

COPY entrypoint.sh /docker-entrypoint.d/entrypoint.sh
