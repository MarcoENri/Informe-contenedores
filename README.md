Práctica de contendores Marco Enriquez
1. Título
Redes contenedores

2. Tiempo de duración
 duracion 24 minutos

3. Fundamentos

En redes de contenedores, la comunicación entre contenedores se facilita mediante la creación de redes virtuales. Docker proporciona herramientas para definir y gestionar estas redes, permitiendo que varios contenedores interactúen entre sí de manera controlada y segura. Al conectar dos o más contenedores en una red local virtual, se facilita el flujo de datos y la colaboración entre aplicaciones distribuidas en un mismo entorno de host o en una red ampliada.

En esta práctica, se configurará una red local para conectar dos contenedores, demostrando cómo Docker gestiona la comunicación interna entre aplicaciones que pueden estar ejecutando servicios diferentes.

4. Conocimientos previos

Conocimientos básicos de Docker: imágenes, contenedores y comandos fundamentales (docker run, docker ps, docker stop, docker rm).
Familiaridad con redes y direcciones IP.
Conocimientos básicos de la línea de comandos.

5. Objetivos a alcanzar

Crear y gestionar una red local de Docker para permitir la comunicación entre contenedores.
Ejecutar y configurar dos contenedores conectados en una red Docker.
Verificar la conectividad y el intercambio de datos entre contenedores en la misma red.

6. Equipo necesario

Computadora con Docker Desktop o Docker Engine instalado y configurado.
WSL 2 (si se trabaja en un sistema operativo Windows 10 o superior).
Acceso a la terminal (cmd, PowerShell, o terminal de Linux).

7. Material de apoyo

Documentación oficial de Docker sobre redes de contenedores: Docker Networking
Docker CLI Reference

8. Procedimiento

Se debe ver la version de dokcer si es que lo tenemos instalado 
![Imagen de WhatsApp 2024-10-28 a las 19 36 17_beaf4ae5](https://github.com/user-attachments/assets/160632df-ccaa-4d82-a5b6-8ec8bf5bfdbc)
 se agrega esl siguiente comando en pantalla para que nos comuniquemos con postgres
Una vez agregado la linea de codigo se comenzara a instalar incluso si no sabemos si esta instalado la imagen usamos docker ps para ver las imagenes descargadas

![Imagen de WhatsApp 2024-10-28 a las 19 36 18_090ba3cf](https://github.com/user-attachments/assets/02b603cf-cc77-4057-b41a-4c319afff1fb)

Usamos la siguiente linea de comando que puede usar cualquier correo electronico que queramos, importante es que deben de acordarse de ese correo y la contraseña de la imagen anterior
![Imagen de WhatsApp 2024-10-28 a las 19 36 18_2525d104](https://github.com/user-attachments/assets/76d18153-4692-4ef4-8851-21c04bc5c593)

Una vez agregado esa linea de codigo, hacemos nuestra propia red: docker network create --attachable redinterna y agregamos las siguientes lineas docker network connect redinterna dbpsql,

docker network connect redinterna pgadmin

![Imagen de WhatsApp 2024-10-28 a las 19 36 18_885a31fc](https://github.com/user-attachments/assets/2d1486ff-b7e9-40cb-8d14-dbebf50d4469)

Despues abrimos el navegador y entramos a lochalhost:8090 que nos lleva a Pgadmin, iniciamos sesion con el correo y la contraseña que hemos agregado anteriormente


![Imagen de WhatsApp 2024-10-28 a las 19 36 18_746ac106](https://github.com/user-attachments/assets/695dba61-8967-4208-af34-68133f552d23)

Una vez dentro Creamos una nueva base

![Captura de pantalla 2024-10-28 193058](https://github.com/user-attachments/assets/5cb8049a-551b-4764-94ab-b81e3117f824)

Dentro de esa base creamos una tabla y le agregamos sus atributos
![Imagen de WhatsApp 2024-10-28 a las 19 36 18_2ddd0cc3](https://github.com/user-attachments/assets/13330e7d-684c-40b2-9c33-69249ede17f9)

![Imagen de WhatsApp 2024-10-28 a las 19 36 19_75db09a3](https://github.com/user-attachments/assets/45a095e1-b48c-485f-8336-9fb9ab1e9609)

9. Resultados esperados

Los dos contenedores estan conectados a la misma red local lo cual es bueno ya que ese es el objetivo de esta practica 

10. Bibliografía
Docker Inc. "Networking overview." Docker Documentation. https://docs.docker.com/network/
Official Docker CLI Reference. Docker Documentation. https://docs.docker.com/engine/reference/commandline/cli/
