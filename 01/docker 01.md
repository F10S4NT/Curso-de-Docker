# Docker

## Docker ports

Para entrar de dentro del contenedor:
>Docker attach

"Cuando se quiere que docker asigne puertos automaticamente se debe de poner -P  mayuscula"

## Docker volumenes

Nos permite compartir archivos y directorios entre contenedores y no perder los datos, por ejemplo de un sql, esto nos ayuda en la persistencia de datos y que no se pierdan cuando matamos un contenedor.

comando de inicio:
>docker volume create --help

Para montarlo en un contenedor:
>docker container -dit -v [VOLUMEN CREADO] [DONDE LO MONTAMOS]

Para compartir archivoe entre contenedores:
>docker container run  -d -v [ruta origen]:[ruta dentro de contenedor archivo con extension] -p
