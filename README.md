# Docker

Wszystkie komendy są odpalane przy budowaniu obrazu (docker build).\
Kontenery bazujące na tym samym obrazie nie zmieniają sobie plików.\
Każda komenda to kolejna warstwa\
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
### `start`
uruchamia zatrzymane kontenery

### `run`
`docker run -p 80:80 -d -rm` \
-rm - kontener zostanie usunięty po tym jak zostanie zatrzymany \
`docker run …` - wchodzi w attached mode I nasłuchuje outputu stdout\
`docker run -d` - detached

### `inspect`
- id
- created date
- konfig 
  - porty
  - env
- entrypoint (CMD)
- wersja
- system
- layers

### `cp`
`docker cp dir/. container_name:/path`\
`docker cp container_name:/path dir/.`

### `images`
lista obrazów

### `ps`
lista uruchomionych kontenerów
`ps -a`lista wszystkich kontenerów

### `name`
`docker run -name wlasna_nazwa`

### `tag`
name:tag - name to nazwa dla grupy obrazów, tag to konkretny obraz\
`node:14`\
`kafka:10`\
używane w `FROM`
`docker build -t app:latest .`
