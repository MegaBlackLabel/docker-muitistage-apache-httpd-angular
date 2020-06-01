FROM node:lts-slim as builder

WORKDIR /frontend

ADD ./frontend/package.json .
ADD ./frontend/package-lock.json .
RUN npm ci
ADD ./frontend/angular.json .
ADD ./frontend/tsconfig.json .
ADD ./frontend/tsconfig.app.json .
ADD ./frontend/src src
RUN npm run build

# builderで作ったファイルをhtdocsにコピーしてApache2サーバを起動するイメージ作成
FROM httpd:alpine as runner

COPY ./frontend/.htaccess /usr/local/apache2/htdocs/
COPY ./frontend/httpd.conf /usr/local/apache2/conf/httpd.conf

COPY --from=builder /frontend/dist/frontend /usr/local/apache2/htdocs/

EXPOSE 80