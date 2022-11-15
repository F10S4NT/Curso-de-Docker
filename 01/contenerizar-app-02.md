# CONTENERIZAR  APP de node express

generar index.js:

>const express = required(´express´)
>
>const app = express()
>
>app.get(´/´, (req,res) => res.send("Hola mundo"))
>
>app.listen(3000, () => console.log("hola"))

Ejecutaremos el siguiente comando para bajar node:
>docker image pull node

checamos comandos:
>docker container run --help

creamos volumen:
>docker run --rm  -w /app -v /home/vagrant/container:/app node

corremos node:
>docker run --rm  -w /app -v /home/vagrant/container:/app -it node

Abrimos bash:
>docker run --rm  -w /app -v /home/vagrant/container:/app -it node bash

Iniciamos node:
>docker run --rm  -w /app -v /home/vagrant/container:/app -it node npm init -y

Instalamos express:
>docker run --rm  -w /app -v /home/vagrant/container:/app -it node npm install -s express

----------------------------------------------------------------------
generamos dockerfile:

>
>FROM node
>
>WORKDIR /app
>
>COPY package.json .
>
>Run npm install
>
>COPY index.js .
>
>CMD ["node","index.js"]
>

Ahora creamos la imagen con nombre web:
>docker image build -t web .

checamos nuestras imagenes:
>docker image ls

Corremos nuestra imagen asignando puertos:
>docker run -t -p 3000:3000 web
