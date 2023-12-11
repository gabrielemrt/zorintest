FROM python:3 AS builder
COPY . /app
WORKDIR /app/doc-custom-app
RUN pip install mkdocs 
ENTRYPOINT [ "mkdocs", "build" ]  

FROM nginx:alpine
COPY --from=builder /app/doc-custom-app/site /usr/share/nginx/html
EXPOSE 80

