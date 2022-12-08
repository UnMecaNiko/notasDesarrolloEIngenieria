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

![image](https://user-images.githubusercontent.com/86577488/205947309-5d8b4a07-fc17-4447-8b19-5b5e47336245.png)

#### Ejemplo en el proyecto del curso

![image](https://user-images.githubusercontent.com/86577488/205987330-7673c803-37ef-46fc-abe5-33dfa9b26273.png)

## RDBMS | Administrador de datos relacionales

Hay dos maneras de acceder a manejadores de bases de datos:

- Instalar en máquina local un administrador de bases relacional.
- Tener ambientes de desarrollo especiales o servicios cloud.
En este curso usaremos MySQL porque tiene un impacto histórico siendo muy utilizado y además es software libre y gratuito. La versión 5.6.43 es compatible con la mayoría de aplicaciones y frameworks.

- Root es el usuario principal que tendrá todos los permisos y por lo tanto en ambientes de producción hay que tener mucho cuidado al configurarlo.

**RDB (relational database)**

**RDBMS (Relational DataBase Management System) Sistema Manejador de Bases de datos relacionales.**

La diferencia entre ambos es que las BBDD son un conjunto de datos pertenecientes ( o al menos en teoría) a un mismo tipo de contexto, que guarda los datos de forma persistente para un posterior uso, y el Sistema de gestión de BBDD o sistema manejador, es el que nos permite acceder a ella, es un software, herramienta que sirve de conexión entre las BBDD y el usuario (nos presenta una interfaz para poder gestionarla, manejarla).

**RDBMS**

- MySQL
- PostgreSQL
- Etc
Todas toman un lenguaje base, pero cada uno lo apropia, imponiéndole diferentes reglas y características.



## Bases de datos no relacionales

- cassandra
- elasticsearch
- neo4j
- MongoDB



## Tipos de Servicios:

- Auto administrados: Es la base de datos que instalas tú y te encargas de actualizaciones, mantenimiento, etc.

- Administrados: Servicios que ofrecen las nubes modernas como Azure y no debes preocuparte por mantenimiento o actualizaciones.

Hoy en día muchas empresas ya no tienen instalados en sus servidores los RDBMS sino que los contratan a otras personas. Estos servicios administrados cloud te permiten concentrarte en la base de datos y no en su administración y actualización.



## Lenguaje SQL

### Historia de SQL

SQL significa Structured Query Language y tiene una estructura clara y fija. Su objetivo es hacer un solo lenguaje para consultar cualquier manejador de bases de datos volviéndose un gran estándar.

Ahora existe el NOSQL o Not Only Structured Query Language que significa que no sólo se utiliza SQLen las bases de datos no relacionales.

### DDL | Data Definition Language

nos ayuda a crear la estructura de una base de datos. Existen 3 grandes comandos:

- Create: Nos ayuda a crear bases de datos, tablas, vistas, índices, etc.
- Alter: Ayuda a alterar o modificar entidades.
- Drop: Nos ayuda a borrar. Hay que tener cuidado al utilizarlo.
3 objetos que manipularemos con el lenguaje DDL:

- Database o bases de datos.
- Table o tablas. Son la traducción a SQL de las entidades.
- View o vistas: Se ofrece la proyección de los datos de la base de datos de forma entendible.

### CREATE VIEW y DDL ALTER

Para agregar la vista de clientes, puedes usar el siguiente código desde la pestaña query 1:

```sql
INSERT INTO `platziblog`.`people` (`person_id`, `last_name`, `first_name`, `address`, `city`) 
VALUES ('1', 'Vásquez', 'Israel', 'Calle Famosa Num 1', 'México'),
	       ('2', 'Hernández', 'Mónica', 'Reforma 222', 'México'),
	       ('3', 'Alanis', 'Edgar', 'Central 1', 'Monterrey');
```

### DDL drop

Está puede ser la sentencia ¡más peligrosa! (????), sobre todo cuando somos principiantes. Básicamente borra o desaparece de nuestra base de datos algún elemento.

### DML

DML trata del contenido de la base de datos. Son las siglas de Data Manipulation Language y sus comandos son:

- Insert: Inserta o agrega nuevos registros a la tabla.
- Update: Actualiza o modifica los datos que ya existen.
![image](https://user-images.githubusercontent.com/86577488/206004346-4258ffd1-eb5c-4b33-9c6e-235a615de9fb.png)
- Delete: Esta sentencia es riesgosa porque puede borrar el contenido de una tabla.
- Select: Trae información de la base de datos.

**ex:**
```sql
INSERT INTO people (last_name,first_name,address, city)
VALUES ('Hernandez','Laura','Calle 21','Monterrey')
```

## Proyecto Platzi Blog

![image](https://user-images.githubusercontent.com/86577488/206464043-6376ac1d-c28a-4ab8-b4bb-762bb63c3943.png)

- Una buena práctica es comenzar creando las entidades que no tienen una llave foránea.
![image](https://user-images.githubusercontent.com/86577488/206466701-2944ee95-304b-4837-ad52-cc620788831d.png)

- Generalmente en los nombres de bases de datos se evita usar eñes o acentos para evitar problemas en los manejadores de las bases de datos.

Ahora se configuran las llaves foráneas.

![image](https://user-images.githubusercontent.com/86577488/206469262-4ef8a116-5f10-4851-8fe8-171596e497f0.png)

Para la relación N a N se debe hacer una tabla intermedia que tenga tres columnas: id, post_id, etiqueta_id. La configuración de las llaves foráneas sería así:

> Las tablas transitivas sirven como puente para unir dos tablas. No tienen contenido semántico.

![image](https://user-images.githubusercontent.com/86577488/206471837-1acb7350-495d-4a20-8ef6-3e59e38e9be6.png)

Ahora que tenemos todo el esquema montado podemos ver la conexión de nuestras tablas de forma gráfica usando la opción de ingeniería inversa.

> Reverse Engineer nos reproduce el esquema del cual nos basamos para crear nuestras tablas. Es útil cuando llegas a un nuevo trabajo y quieres entender cuál fue la mentalidad que tuvieron al momento de crear las bases de datos.

![image](https://user-images.githubusercontent.com/86577488/206472147-1cb66142-fa3d-4611-9f34-c891334060b0.png)





## Consultas (Querys) a una base de datos

Las consultas o queries a una base de datos son una parte fundamental ya que esto podría salvar un negocio o empresa.
Alrededor de las consultas a las bases de datos se han creado varias especialidades como ETL o transformación de datos, business intelligence e incluso machine learning.

Los queries son la forma en la que estructuramos las preguntas que se harán a la base de datos. Transforma preguntas en sintaxis.

El query tiene básicamente 2 partes: SELECT y FROM y puede aparecer una tercera como WHERE.

- La estrellita o asterisco (\*) quiere decir que vamos a seleccionar todo sin filtrar campos.

![image](https://user-images.githubusercontent.com/86577488/206473971-2748e767-33d1-4252-91f6-694fed651583.png)


### SELECT
Se encarga de proyectar o mostrar datos.

- El nombre de las columnas o campos que estamos consultando puede ser cambiado utilizando AS después del nombre del campo y poniendo el nuevo que queremos tener:

```sql
SELECT titulo AS encabezado
FROM posts;
```
- Existe una función de SELECT para poder contar la cantidad de registros. Esa información (un número) será el resultado del query:

```sql
SELECT COUNT(*)
FROM posts;
```

### FROM

FROM indica de dónde se deben traer los datos y puede ayudar a hacer sentencias y filtros complejos cuando se quieren unir tablas. La sentencia compañera que nos ayuda con este proceso es JOIN.

![image](https://user-images.githubusercontent.com/86577488/206533579-e44ba701-43dd-4666-8769-dbeddaa20f10.png)

Los diagramas de Venn son círculos que se tocan en algún punto para ver dónde está la intersección de conjuntos. Ayudan mucho para poder formular la sentencia JOIN de la manera adecuada dependiendo del query que se quiere hacer.

```sql
SELECT	*
FROM	usuarios 
	JOIN posts on usuarios.id = posts.usuario_id;
```

### WHERE

WHERE es la sentencia que nos ayuda a filtrar tuplas o registros dependiendo de las características que elegimos.+

- La propiedad LIKE nos ayuda a traer registros de los cuales conocemos sólo una parte de la información.
- La propiedad BETWEEN nos sirve para arrojar registros que estén en el medio de dos. Por ejemplo los registros con id entre 20 y 30.

### NULL | NOT NULL

El valor nulo en una tabla generalmente es su valor por defecto cuando nadie le asignó algo diferente. La sintaxis para hacer búsquedas de datos nulos es IS NULL. La sintaxis para buscar datos que no son nulos es IS NOT NULL.

```sql
select * 
from posts 
where usuario_id is not null
```

### GROUP BY

GROUP BY tiene que ver con agrupación. Indica a la base de datos qué criterios debe tener en cuenta para agrupar.

```sql
SELECT 
    MONTHNAME(fecha_publicacion) fechita, COUNT(*) post_quantity
FROM
    posts
GROUP BY fecha_publicacion
```

# Helpful Links

- [Codd's 12 rules](https://www.w3resource.com/sql/sql-basic/codd-12-rule-relation.php)

- [MySQL What is DDL, DML and DCL](https://www.w3schools.in/mysql/ddl-dml-dcl/)

- [GenerateData](https://generatedata.com/)

