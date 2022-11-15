# Creando redes en docker

la red mas usada es bridge,

creamos con nano dockerfile y ponemos lo siguiente:
>RUN apt-get update && apt-get install net tools iputils-ping -y

construimos la imagen:
>docker image build -t ubunto-tools .

generando red
>docker network

checamos comandos:
>docker network create --help

creamos una red con nombre br0:
>docker network create br0

checamos redes
>docker network ls

inspeccionamos nuestra red creada:
>docker network inspect br0

generar contenedor

checamos nuestros contenedores:
>docker container ls

corremos nuestro contenedor asignando a una red y un nombre:
>docker container -run -dit --network br0 --name host1 ubunto-tools

corremos nuestro contenedor asignando a una red y un nombre:
>docker container -run -dit --network br0 --name host2 ubunto-tools

checamos nuestros contenedores:
>docker container ls

ejecutamos un bash dentro de nuestro contenedor
>docker container exec -it host1 bash

hacer ping entre contenedores
>$ping host2
