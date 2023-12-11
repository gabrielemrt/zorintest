# Dockerfile per l'immagine di Nginx con il sito Mkdocs compilato
FROM python:3 AS builder

# Imposta il working directory all'interno del container
WORKDIR /app/doc-custom-app

# Copia i sorgenti dal repository al container
COPY . /app

# Installa le dipendenze necessarie per la compilazione
RUN pip install mkdocs

# Compila la documentazione
RUN mkdocs build


# Secondo stage per l'immagine di Nginx
FROM nginx:alpine

# Copia il sito compilato dalla fase precedente
COPY --from=builder /app/doc-custom-app/site /usr/share/nginx/html

# Esponi la porta 80
EXPOSE 80

# Comando di avvio di Nginx
CMD ["nginx", "-g", "daemon off;"]
