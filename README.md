# 2023f1grid
búsqueda de información sobre el grid F1

## run F1 grid API 
1. npm i for the package.json to install all necessary dependencies and libraries
2. docker pull mongo
3. docker netwwork create my-test-network
4. docker run --name bootcamp --hostname cluster0.dnvlpam.mongodb.net -d -p 27017:27017 --network my-test-network
5. docker cp C:\Users\theve\OneDrive\Documents\cowde\prueba1DOCKER-bootcamp-javierflores\db-sample\2023f1grids.json bootcamp:/2023f1grids.json
6. docker exec -it bootcamp mongoimport --db bootcamp --collection 2023f1grids --file /2023f1grids.json --jsonArray
    // para el paso anterior, el contenedor se llama bootcamp y la collection de la base de datos se llama 2023f1grids. Asimismo, mi base de datos en mongo se llama bootcamp.
    ## con los pasos anteriores, mi contenedor "bootcamp" con mi imagen "mongo" ha sido creada y confirmé que mis datos se han cargado correctamente. Ahora procedemos a dockerizar el API de consulta de la F1 grid

# para crear el archivo server.js se tomó de base el ejemplo del repo compartido por profesor, y se cambió el método GET
    - Para poder crear la imagen fue necesario abrir terminal interna desde la carpeta docker:
    docker build -t mongo . 
    // para el caso mongo era el nombre de mi imagen. 
    // notar que el comando COPY package*.json no me funcionó, hubo que copiar directamente los archivos ya que recibía error en el RUN npm install

docker run -p 8080:8080 -d --name api-test --network my-test-network mongo .
docker ps
