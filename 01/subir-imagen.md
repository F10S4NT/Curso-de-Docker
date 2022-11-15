# SUBIR IMAGEN A DOCKER HUB

Nos logeamos:
>docker login

checamos nuestras imagenes:
>docker image ls

checamos comandos para subir:
>docker push --help

al dar este comando nos aparecera un error, debido a que no es una imagen oficial.
>docker push web

checamos comando flag tag:
>docker tag --help

le pasamos nuestro usuario:
>docker tag web [USUARIO]/node_app

checamos nuestras imagenes y nos asegramos que ya este:
>docker image ls

y finalmente subimos nuestra imagen a docker hub:
>docker push
