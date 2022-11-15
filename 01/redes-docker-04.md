# Redes en docker

Inspeccion de redes-genera 3 redes bridge, host, none

para ver ejecutamos:
>docker network

vemos las redes generadas
>docker network ls

inspeccionamos a bridge:
>docker network inspect bridge

ejecutamos para asignar red a contenedor *no es necesario hacerlo:
>docker container run -dit --network bridge ubunto

inpseccionamos redes:
>docker network inpsector

desconctamos el contenedor:
>docker network disconnect bridge [ID_CONTENEDOR]

lo volvemos a conecttar:
>docker network connect bridge [ID_CONTENEDOR]

Antes de agregar contenedores a alguna red se deben de detener

vemos contenedores:
>docker ps -q

iniciamos contenedpres conectadno a red
>docker run -dit none ubunto host

inpseccionamos a red none:
>docker network inspect none

ejecutamos un bash:
>docker container execute ubunto bash

necesario net tools, lo instalamos
