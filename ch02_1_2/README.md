## build docker image
```
docker image build -t example/echo:latest .
```

## run container
```
docker container run example/echo:latest
```

## run container as daemon
```
docker container run -d example/echo:latest
```

## access container
```
curl http://localhost:8080/

curl: (52) Empty reply from server
```

## port forwarding
```
docker container run -d -p 9000:8080 example/echo:latest

docker container ls

CONTAINER ID        IMAGE                 COMMAND                  CREATED              STATUS              PORTS                    NAMES
37e2b10b00e7        example/echo:latest   "go run /echo/main.go"   About a minute ago   Up About a minute   0.0.0.0:9000->8080/tcp   competent_leakey
```

## retry access container
```
curl http://localhost:9000/

Hello Docker!!
```

## stop container
```
docker stop 37e2b10b00e7cb558db6c5c60ccb1fc72318b68e47980f51e23c0492607b7b84
```
