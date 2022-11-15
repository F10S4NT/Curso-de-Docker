# docker compose redes

levantamos compose:
>docker compose up -d

inspeccionamos redes:
docker network inspect

inpspeccionamos:
>docker inspect compose_default

En nuestro archivo docker-compose.yml agregamos networks:

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

            networks: 

                - lorem

            environment:

                MYSQL_ROOT_PASSWORD: ${MYSQL_ROOT_PASSWORD}

    networks:

        lorem: 

            driver: bridge

agregar servicios a red existente en este caso a b0 y le indicamos true en external

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

            networks: 

                - b0

            environment:

                MYSQL_ROOT_PASSWORD: ${MYSQL_ROOT_PASSWORD}

    networks:

        b0: 

            external: true

levantamos compose:
>docker-compose up -d

inspeccionamos nuestra red b0:
>docker inspec b0
