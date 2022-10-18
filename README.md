# Docker

Wszystkie komendy są odpalane przy budowaniu obrazu (docker build).\
Kontenery bazujące na tym samym obrazie nie zmieniają sobie plików.\
## Dockerfile
### `WORKDIR`
wszystkie koemndy odpalane będą tutaj

### `COPY . /app`
mimo że wcześniej jest WORKDIR to można dodac tutaj /app tak żeby było jasne gdzie to jest kopiowane, można dać też `COPY . .`

### `CMD` 
odpalane nie przy tworzeniu obrazy a przy instancjonowaniu kontenera
```dockerfile
CMD ["program", "argumenty"]
CMD ["node", "server.js"]
CMD ["python", "program.py"]
```

### `EXPOSE`
pokazuje na jakich portach powinno ustawić się publish

## docker CLI
### `RUN`
`docker run -p 80:80 -d -rm` \
-rm - kontener zostanie usunięty po tym jak zostanie zatrzymany \
`docker run …` - wchodzi w attached mode I nasłuchuje outputu stdout\
`docker run -d` - detached
