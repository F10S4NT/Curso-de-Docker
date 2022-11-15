# CONTENERIZAR  APP de node express

generar index.js:

>const express = required(´express´)
>
>const app = express()
>
>app.get(´/´, (req,res) => res.send("Hola mundo"))
>
>app.listen(3000, () => console.log("hola"))

Ejecutaremos el siguiente comando:

>docker image pull node

# docker container run --help

# docker run --rm  -w /app -v /home/vagrant/container:/app node

# docker run --rm  -w /app -v /home/vagrant/container:/app -it node

# docker run --rm  -w /app -v /home/vagrant/container:/app -it node bash

# docker run --rm  -w /app -v /home/vagrant/container:/app -it node npm init -y

# docker run --rm  -w /app -v /home/vagrant/container:/app -it node npm install -s express






generar dockerfile


----------------------------------------------------------------------
FROM node

WORKDIR /app

COPY package.json .

Run npm install

COPY index.js .

CMD ["node","index.js"]

------------------------------------------------------------------------





#docker image build -t web .

#docker image ls


#docker run -t -p 3000:3000 web



