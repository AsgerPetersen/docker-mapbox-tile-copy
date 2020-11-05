# docker-mapbox-tile-copy
mapbox-tile-copy dockerized

Wraps https://github.com/mapbox/mapbox-tile-copy in docker for convenient usage.

Dockerfile work primarily done by @kjoller - thank you 😀.


Usage example:
```
export AWS_ACCESS_KEY_ID=XXXXXX
export AWS_SECRET_ACCESS_KEY=YYYYY
docker run --rm -it  -v "$(pwd)":/data  -e AWS_ACCESS_KEY_ID=$AWS_ACCESS_KEY_ID -e AWS_SECRET_ACCESS_KEY=$AWS_SECRET_ACCESS_KEY asgerpetersen/mapbox-tile-copy mapbox-tile-copy /data/xxx/tiles.mbtiles s3://mybucket/folder/{z}/{x}/{y}
```

Current working directory is mapped to the absolute path `/data` in the container.

Entrypoint stuff could probably be done in a smarter way, but this at least works 😀