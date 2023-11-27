# Link
https://github.com/fondazioneedulife/zorintest/blob/main/esame.md

# Contesto
Mkdocs è una libreria python per la generazione di documentazione, il team di sviluppo ha completato la stesura della documentazione per il progetto e ha fornito un repository con i sorgenti.

Si vuole andare in produzione in pochi giorni e per compliance ISO è richiesta la disponibilità della documentazione.

Compito dei componenti Ops del team è predisporre immagine versionata e immutabile della documentazione in un dato momento.

# Utilizzare il repository dei sorgenti fornito e predisporre le seguenti attività

* [40 pt] immagine docker nginx con il sito compilato ed esposto
  * occorre prestare attenzione alla  dimensione dell'immagine
  * i sorgenti vanno presi dal tag 1.0.0 del repository

> creo il Dockerfile con all'interno l'Ngnix 

> sucessivamente bildo l'immagine docker `docker build -t dockesame:1.0.0 .`

> infine ranno il container `docker run -p 80:80 dockesame:1.0.0`


* [50 pt] docker stack con:
  * una replica
  * i limits delle risorse impostate a min 50 MB e max 100MB
  * limits nella dimensione dei log

> all'interno della repository creo il docker-compose e lo compilo 

> sucessivamente faccio partire lo stack `docker stack deploy -c docker-compose.yaml ESAMEE`

> infine verifico che il sito sia raggiungibile e poi verifico lo stato dello stack con `docker stats esame_mkdocs-TABB`


* [10 pt] Aggiungere al repository un devcontainer per l'esecuzione locale, riutilizzando il dockerfile già predisposto al punto 1. Taggare i sorgenti con il tag 2.0.0
