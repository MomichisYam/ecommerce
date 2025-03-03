# Tabla de Artistas Grupales 

Un artísta puede tomar 2 roles , ser un **Artista grupal** ó un **Artista individual**, un artista grupal es un tipo de  
artista que toma el rol de una banda o un conjunto de artístas que se agrupan para crear canciones o álbumes.

> Un artista grupal puede contener varios Integrantes_grupo

## Columnas de artista grupal

* **IDGrupo**: Es la clave primaria (PRIMARY KEY) de la tabla, que identifica de 
manera única cada grupo. Está definida como un campo de tipo INT.
* **FechaCreacion**: Un campo de tipo INT que representa la fecha de creación del grupo. 
En este caso, el tipo INT probablemente se utiliza para almacenar la fecha en un 
formato numérico (por ejemplo, YYYYMMDD).

### Ejemplo 

| ID | Nombre | Año de creación |
|-|-|-|
| 6 | Rondalla de Saltillo | 1996 |

### Relaciones de llave foranea 

* **FOREIGN KEY (IDGrupo) REFERENCES Artista(ID)** : Aquí, la 
columna IDGrupo de la tabla Grupo está definida como una clave foránea que 
hace referencia a la columna ID de la tabla Artista. Esto implica que cada 
grupo está asociado con un solo artista.

### Restricciones 

* **La restricción ON DELETE CASCADE** asegura que si un artista es eliminado 
de la tabla Artista, todos los grupos asociados a ese artista también serán 
eliminados de la tabla Grupo.
* **La restricción ON UPDATE CASCADE** garantiza que si el ID de un artista 
en la tabla Artista se actualiza, esta actualización se reflejará automáticamente 
en la tabla Grupo. 
