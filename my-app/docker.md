## Build an image
docker build . -t myapp:2.0

## Run Image

docker run -p 3001:3000 -d  myapp:2.0

## Remove all unused containers
docker system prune