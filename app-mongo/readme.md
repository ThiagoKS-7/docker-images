## Como integrar front e banco de dados com docker 

### Fazer pull das images

docker pull mongo:4.4.6
docker pull aluradocker/alura-books:1.0

### Criar network

docker network create --driver bridge network-name

### Criar imagem do banco

docker run -d --network network-name --name meu-mongo -v /home/thiago/Linux/docker/mongo-aula/database:/data/db mongo:4.4.6

### Criar imagem do app

docker run -d --network network-name --name alura-books -p 3000:3000 aluradocker/alura-books:1.0

### Para conferir dados usando o mongosh

entrar no container mongo
mongo "mongodb://meu-mongo:27017/alura-books"
show collections
db.collection.find()
