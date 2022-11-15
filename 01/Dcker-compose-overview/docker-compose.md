# Docker compose overview

Buscaer en google docker compuse y lo instalamos

checamos nueswtra version:
>docker-compose --version

<p>creamos un docker-compose.yml:</p>

<pre><code>
    version:

    services:

        nginx:
            image: nginx

            ports:

                -"80:80"
</code></pre>

levntamso con el erahcivo creado
>docker-compose up

checamos comandos:
>docker-compose up --help

corremos nuestro compose:
>docker-compose -d

listamos los compose que tenemos:
>docker-compose ls


podemos destruir contenedores:
>docker-compose ps

    version:


    services:

        nginx:
            image: nginx

            container-name: nginx

            ports:

                -"80:80"

checamos nuestro compose:
>docker-compose ps

corremos nuestro compose con -d:
>docker-compose -d

checamos compose corriendo:
>docker-compose ps

agregamos mysql a nuestro archivo docker-compose.yml:

    version:




    services:

        nginx:
            image: nginx

            container-name: nginx

            ports:

                -"80:80"


        mysql:
            image:mysql

            container-name: mysql

levantamos nuevamente el archivo yml y vemos que agrega mysql:
>docker-compose up -d

checamos compose corriendo:
>docker-compose ps

checamos contenedores:
>docker ps

checamos todos los contenedores:
>docker ps-a

debemos de ir checando los logs por cualquier error:
>docker-compose logs mysql

podemos eliminar contenedores con este comando:
>docker-compose down

## definir variables de entorno dentor de compose

    version:




    services:

        nginx:
            image: nginx

            container-name: nginx

            ports:

                -"80:80"


        mysql:
            image:mysql

            container-name: mysql

            environment: 
                MYSQL_ROOT_PASSWORD: root

al correr sql nos dio error porque no le pasamos el password, le agregamos y lo levantamos:
>docker-compose up -d

checamos nuestros compose:
>docker-compose ps

## agregando puertos a mysql

    version:




    services:

        nginx:
            image: nginx

            container-name: nginx

            ports:

                -"80:80"


        mysql:
            image:mysql

            container-name: mysql

            ports:
                - "3306:3306"

            environment: 
                MYSQL_ROOT_PASSWORD: root

agregamos los puertos en donde trabajara mysql y levantamos otra vez:
>docker-compose up

checamos:
>docker-compose ps
