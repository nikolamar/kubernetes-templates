# Nodejs service


## Create service


Build docker image
```
docker buildx build --push --platform linux/arm64,linux/amd64 --tag docker-repository/nodejs-express:0.0.1 .
```


Push docker image
```
docker push docker-repository/nodejs-express:0.0.1
```


Specify your image in deployment.yaml file and create app with Kubernetes
```
kubectl apply -f application.yaml 
```


## Run with docker


Run with docker cli
```
docker run --rm -it -p 127.0.0.1:3000:3000 docker-repository/nodejs-express:0.0.1
```


Run with docker cli using docker-compose.yaml file
```
docker compose --env-file .env up --build
```