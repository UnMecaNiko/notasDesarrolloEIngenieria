# Curso de Docker

Éste es un curso sobre los fundamentos de Docker, tanto para quienes no conocen esta tecnología y quieren aprender a usarla como para quienes la usan frecuentemente pero quieren profundizar en los detalles de cómo funciona en detalle y cómo puede ayudarles a aprovechar al máximo la herramienta en sus desarrollos profesionales.

- Conocer la filosofía del trabajo en Docker.
- Aplicar las buenas prácticas de Docker.

Lo que verás a continuación son mis notas del [curso](https://platzi.com/cursos/docker/) 🚀🚀

## Las tres áreas en el desarrollo de software profesional

### Problems when building:
- Development dependencies (packages)
- Runtime versions
- Equivalence of development environments (code sharing)
- Equivalence of production environments(go to production)
- Versions / compatibility(integration of other services e.g.: databases)

### Problems when distributing:
- Different build generations
- Access to production servers
- Native vs. distributed execution
- Serverless

### Problems when executing:
- Application dependencies
- Operating System Compatibility
- Availability of external services
- Hardware Resources

### Docker allows:
Build, distribute and run your code anywhere without worrying.

## Virtualización

Es la versión virtual de algún recurso tecnológico ya sea hardware, software, el concepto de una máquina ETC.

**Problemas:**
- Peso: se repitten archivos comunes, inicio lento, orden de los gb.
- Costo de administracion: necesita mantenimiento.
- Multiples formatos: tienen distintas formas de empaquetar el SW.

Estos problemas con Docker, desaparecen porque utiliza contenedores.

## Contenerdores

A diferencia de la virtualización de una VM las cuál es la versión virtual de una máquina, computador o servidor. Un contenedor solamente virtualiza lo estrictamente necesario para que el código sea ejecutado.

Unidad lógica, agrupación de procesos.

### ¿Que es un contenedor?

- Es una agrupación de procesos.

- Es una entidad lógica, no tiene el limite estricto de las máquinas virtuales, emulación del sistema operativo simulado por otra más abajo.

- Ejecuta sus procesos de forma nativa.

- Los procesos que se ejecutan adentro de los contenedores ven su universo como el contenedor lo define, no pueden ver mas allá del contenedor, a pesar de estar corriendo en una maquina más grande.

- No tienen forma de consumir más recursos que los que se les permite. Si esta restringido en memoria ram por ejemplo, es la única que pueden usar.

- A fines prácticos los podemos imaginar cómo maquinas virtuales, pero NO lo son. Máquinas virtuales livianas.

- Docker corre de forma nativa solo en Linux.

- Sector del disco: Cuando un contenedor es ejecutado, el daemon de docker le dice, a partir de acá para arriba este disco es tuyo, pero no puedes subir mas arriba.

- Docker hace que los procesos adentro de un contenedor este aislados del resto del sistema, no le permite ver más allá.

- Cada contenedor tiene un ID único, también tiene un nombre.

### Ventajas de los contenedores

- flexibles: cualquier aplicación que quieras meter en un contenedor se puede meter en un contenedor.
- livianos: reutilizar kernel para ejecutar el código sin necesidad de tener un sistema operativo completo.
- portables: se pueden ejecutar en cualquier máquina, tranquilo están diseñados para eso.
- bajo acoplamiento: tiene todo lo necesario para correr el código que está dentro de sí mismo sin necesidad de afectar a otros contenedores.
- escalables: se pueden crear varios contenedores sin el temor de que esto afecte el rendimiento o funcionamiento de los mismos.
- seguros: solo puede acceder a lo necesario para ejecutar el código. Un contenedor no puede acceder a otro contenedor, ni al sistema operativo que lo ejecuta.

## Command window

`docker ps`: Obtenemos información acerca de los contenedores que están corriendo

`docker ps -a`: Obtenemos información acerca de todos los contenedores que se han corrido a traves del tiempo.

`docker inspect {{CONTAINER ID}}` información sobre un contenedor en específico.

`docker container prune` Eliminar todos los contenedores

`docker run -it ubuntu` correr un sistema linux dentro de la linea de comandos a través de docker.

`docker stop <container_id or container_name>` parar un container

### Exponiendo contenedores

`docker run -d --name proxy nginx `(corro un nginx)

`docker stop proxy` Apaga el contenedor

`docker rm -f <contenedor>` (lo para y lo borra)

`docker run -d --name proxy -p 8080:80 nginx` corro un nginx y expongo el puerto 80 del contenedor en el puerto 8080 de mi máquina

`docker logs proxy` Veo los logs

`docker logs --tail 10 -f proxy` veo y sigo solo las 10 últimas entradas del log

# Helpful Links

- [Play with Docker](https://labs.play-with-docker.com/)