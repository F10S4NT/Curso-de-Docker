# Docker compose Variables de entorno

 En el archivo docker-compose.yml cambiamos MYSQL_ROOT_PASSWORD: root por MYSQL_ROOT_PASSWORD: ${MYSQL_ROOT_PASSWORD} esto para mandarlo a otro archivo llamada .env

    version: 



    services:

        nginx: nginx

        container_name: nginx

        ports:
        
            -"80:80"

        mysql:
            
            image: mysql

            container_name: mysql

            ports:

                -"3306:3306"

            environment:

                MYSQL_ROOT_PASSWORD: ${MYSQL_ROOT_PASSWORD}

creamos el archivo .env y colocamos la varible para pasarle al docker-compose.yml
>MYSQL_ROOT_PASSWORD=root

levantamos compose:
>docker-compose up -d

checamos compose
>docker-compose ps
