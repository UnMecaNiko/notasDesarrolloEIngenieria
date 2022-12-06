# Curso de Fundamentos de Bases de Datos

Antes de utilizar cualquier tecnología para bases de datos debes entender los fundamentos de diseño y modelado requeridos para que tengas la mejor arquitectura posible. Crea tus propios modelos de bases de datos con las mejores prácticas desde cero.

- Teoría general de Bases de Datos
- Bases de Datos Relacionales
- Bases de Datos no Relacionales
- Otros tipos de Bases de Datos

Estas son mis notas del [curso](https://platzi.com/cursos/bd/), espero te sirvan 🚀
    
## Bases de datos relacionales

Su principal fundamenta es la algebra relacional. Algunos ejemplos son:

- SQL server
- Oracle
- PostgresQl
- MySQL
- MariaDB

### Historia 

Creador: Dr. Edgar Frank Codd
Nacen de la necesidad de de tener un sistema más organizado que el almacenamiento en archivos, que consistía en archivos de texto plano donde se plasmaba información separada por comas, esto era dificil de sostener

### Entidades y atributos

En bases de datos, una entidad es la representación de un objeto o concepto del mundo real que se describe en una base de datos. Las entidades se describen en la estructura de la base de datos empleando un modelo de datos.

### Entidad
Una entidad es algo similar a un objeto (programación orientada a objetos) y representa algo en el mundo real, incluso algo abstracto. Tienen atributos que son las cosas que los hacen ser una entidad y por convención se ponen en plural.

**Ejemplo de entidad en bases de datos**

En la imagen puedes observar como ejemplo que la enidad Laptops posee diferentes atributos como colo, pantalla, año, modelo, etc.

![](https://static.platzi.com/media/user_upload/ejemplo%20de%20entidad-c0b48b06-ba54-4026-add0-e7e522d6f47e.jpg)

#### Tipos de entidades

**Entidades fuertes**: son entidades que pueden sobrevivir por sí solas.

**Entidades débiles**: no pueden existir sin una entidad fuerte y se representan con un cuadrado con doble línea.

- Identidades débiles por identidad: no se diferencian entre sí más que por la clave de su identidad fuerte.
- Identidades débiles por existencia: se les asigna una clave propia.

### Atributo

Son las características o propiedades que describen a la entidad (se encierra en un óvalo). Los atributos se componen de:

Los atributos compuestos son aquellos que tienen atributos ellos mismos.

Los atributos llave son aquellos que identifican a la entidad y no pueden ser repetidos. Existen:

- Naturales: son inherentes al objeto como el número de serie
- Clave artificial: no es inherente al objeto y se asigna de manera arbitraria.

### Relaciones

Las relaciones nos permiten ligar o unir nuestras diferentes entidades y se representan con rombos. Por convención se definen a través de verbos.

Las relaciones tienen una propiedad llamada cardinalidad y tiene que ver con números. Cuántos de un lado pertenecen a cuántos del otro lado:

- Cardinalidad: 1 a 1
- Cardinalidad: 0 a 1
- Cardinalidad: 1 a N
- Cardinalidad: 0 a N

### Diagrama ER

Un diagrama es como un mapa y nos ayuda a entender cuáles son las entidades con las que vamos a trabajar, cuáles son sus relaciones y qué papel van a jugar en las aplicaciones de la base de datos.

![image](https://user-images.githubusercontent.com/86577488/205941992-9287147a-b7b2-42d2-ac9b-3ef89706497c.png)

### Tipos de datos y constraints

Para llevar a la práctica un diagrama debemos ir más allá y darle detalle con parámetros como:

**Tipos de dato:**

- Texto: CHAR(n), VARCHAR(n), TEXT
- Números: INTEGER, BIGINT, SMALLINT, DECIMAL(n,s), NUMERIC(n,s)
- Fecha/hora: DATE, TIME, DATETIME, TIMESTAMP
- Lógicos: BOOLEAN

**Constraints (Restricciones)**

- NOT NULL: Se asegura que la columna no tenga valores nulos
- UNIQUE: Se asegura que cada valor en la columna no se repita
- PRIMARY KEY: Es una combinación de NOT NULL y UNIQUE
- FOREIGN KEY: Identifica de manera única una tupla en otra tabla
- CHECK: Se asegura que el valor en la columna cumpla una condición dada
- DEFAULT: Coloca un valor por defecto cuando no hay un valor especificado
- INDEX: Se crea por columna para permitir búsquedas más rápidas


### Diagrama Físico: normalización

La normalización como su nombre lo indica nos ayuda a dejar todo de una forma normal. Esto obedece a las 12 reglas de Codd y nos permiten separar componentes en la base de datos:

- Primera forma normal (1FN): Atributos atómicos (Sin campos repetidos)
- Segunda forma normal (2FN): Cumple 1FN y cada campo de la tabla debe depender de una clave única.
- Tercera forma normal (3FN): Cumple 1FN y 2FN y los campos que NO son clave, NO deben tener dependencias.
- Cuarta forma normal (4FN): Cumple 1FN, 2FN, 3FN y los campos multivaluados se identifican por una clave única.



## Bases de datos no relacionales

- cassandra
- elasticsearch
- neo4j
- MongoDB

## Tipos de Servicios:

- Auto administrados: Es la base de datos que instalas tú y te encargas de actualizaciones, mantenimiento, etc.
- Administrados: Servicios que ofrecen las nubes modernas como Azure y no debes preocuparte por mantenimiento o actualizaciones.

# Helpful Links

- [Codd's 12 rules](https://www.w3resource.com/sql/sql-basic/codd-12-rule-relation.php)
