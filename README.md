Build:
npm run build
docker build -f Dockerfile.prod -t hello-docker-build .
docker container run --rm -p 80:5000 hello-docker-build

Dev:
docker build -f Dockerfile -t hello-docker-dev .
docker container run -it --rm -v ${PWD}:/app -v /app/node_modules -p 3001:3000 -e CHOKIDAR_USEPOLLING=true hello-docker-dev
