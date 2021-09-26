FROM node:14.17.6 as builder
WORKDIR /angular-docker
COPY . .
RUN npm install

RUN npm run build --prod

# Stage 2
FROM nginx


COPY --from=builder /angular-docker/dist/*  /usr/share/nginx/html/
EXPOSE 80
