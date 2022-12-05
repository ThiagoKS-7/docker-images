## Como criar containers Ubuntu com a mesma network via terminal

### Criar network

docker network create --driver bridge network-name

### Criar imagem do server

docker run -it --name server --network network-name ubuntu bash
apt-get update
apt-get install iputils-ping -y
ping client

### Criar imagem do cliente

docker run -it --name server --network network-name ubuntu bash

### Criar imagem do cliente

docker run -d --name client --network network-name ubuntu sleep 1d