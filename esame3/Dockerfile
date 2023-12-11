FROM node:lts-alpine AS builder
WORKDIR /app
RUN npm install -g @angular/cli \
    && ng new hello-world \
    && cd hello-world \
    && ng build

FROM nginx:alpine
COPY --from=builder  /app/hello-world/dist/hello-world/browser /usr/share/nginx/html
EXPOSE 80
ENTRYPOINT [ "nginx", "-g",  "daemon off;" ]


#docker build -t exam3:v1.0.0 . 
#docker run -d -p 4200:80 exam3:v1.0.0