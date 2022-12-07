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

### Ventajas de los contenedores

- flexibles: cualquier aplicación que quieras meter en un contenedor se puede meter en un contenedor.
- livianos: reutilizar kernel para ejecutar el código sin necesidad de tener un sistema operativo completo.
- portables: se pueden ejecutar en cualquier máquina, tranquilo están diseñados para eso.
- bajo acoplamiento: tiene todo lo necesario para correr el código que está dentro de sí mismo sin necesidad de afectar a otros contenedores.
- escalables: se pueden crear varios contenedores sin el temor de que esto afecte el rendimiento o funcionamiento de los mismos.
- seguros: solo puede acceder a lo necesario para ejecutar el código. Un contenedor no puede acceder a otro contenedor, ni al sistema operativo que lo ejecuta.

