# Agregando Ip estática a contenedor

checamos oopciones de comandos:
>docker network --help

creamos un subnet con nombre br02:
>docker network create --subnet 10.1.0.0/24 --gateway 10.1.0.1 br02

checamos nuestras redes:
>docker network ls

inspeccionamos nuestra subnet creada:
>docker inspect br02

generando contenedor con ip estatica
>docker container run -it --ip 10.1.0.10 --network br02 ubunto-tools

inspeccionamos nuestra subnet y comprobamos:
>docker inspect br02
