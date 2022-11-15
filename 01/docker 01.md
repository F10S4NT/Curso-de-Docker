# Docker

## Docker ports

Para entrar de dentro del contenedor:
>Docker attach

"Cuando se quiere que docker asigne puertos automaticamente se debe de poner -P  mayuscula"

## DOCKER commits

Los commit que se realizan son de cuando modificamos algo dentro del contenedor
y deseamos guardarlo y utilizro multiples veces y poder usarlo como una imagen.

>docker container commit [ID_CONTENEDOR] [nombre que le damos]

## Docker volumenes

Nos permite compartir archivos y directorios entre contenedores y no perder los datos, por ejemplo de un sql, esto nos ayuda en la persistencia de datos y que no se pierdan cuando matamos un contenedor.

comando de inicio:
>docker volume create --help

Para montarlo en un contenedor:
>docker container -dit -v [VOLUMEN CREADO] [DONDE LO MONTAMOS]

Para compartir archivoe entre contenedores:
>docker container run  -d -v [ruta origen]:[ruta dentro de contenedor archivo con extension] -p

## Dockerfile

Trabajremos con los archivos dockerfile. creamos un archivo con nombre dockerfile

Directivas en mayuscula
ejemplo:
>FROM ubunto  
>
>RUN mkdir app
>
>RUN cd /app && touch data  

Ejecutamos el siguiente comando:
>docker image build [OPTIONS] PATH | URL | -t

Para constriur ejecutamos y le damos el nombre de ubunto-file-2:
>docker image build -t ubunto-file-2 .
