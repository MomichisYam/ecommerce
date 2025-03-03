# Tabla de Integrante_grupo

Esta tabla corresponde a los integrantes que se contienen en un artísta grupal, o se puede entender  
como los artístas que comforman un grupo o una agrupación, como las bandas. 

## Columnas de Integrante_grupo

* **IDGrupo**: Este atributo es de tipo INT y se utiliza para identificar de manera única a 
un grupo dentro de la tabla Integrante_Grupo. Representa la clave primaria del grupo 
al que pertenece el integrante. Además, actúa como una clave foránea, ya que hace 
referencia a la columna IDGrupo en la tabla Grupo. Este campo es crucial para 
establecer la relación entre un integrante y el grupo al que pertenece.
* **NombreIntegrante**: Este atributo es de tipo VARCHAR(55) y almacena el nombre 
del integrante del grupo. Tiene una longitud máxima de 55 caracteres, lo cual es 
suficiente para nombres completos de integrantes. Se establece con la restricción 
NOT NULL, lo que significa que este campo no puede quedar vacío al insertar un 
registro. Este campo, junto con IDGrupo, forma la clave primaria compuesta de la 
tabla, asegurando que no haya duplicados de un integrante en un mismo grupo.

### Ejemplo 

| ID | Nombre | Nombre Grupo |
|-|-|-|
| 6 | Adam Hann | The 1975 |

### Relaciones de llaves foráneas

* **FOREIGN KEY (IDGrupo) REFERENCES Grupo(IDGrupo)**: Este atributo 
establece una relación de clave foránea entre la tabla Integrante_Grupo y la tabla 
Grupo. La columna IDGrupo en Integrante_Grupo hace referencia a la columna 
IDGrupo en la tabla Grupo, lo que asegura que un integrante solo pueda ser asociado 
a un grupo existente. Esta relación garantiza la integridad referencial entre ambas 
tablas.

### Relaciones de actualización y eliminación 

* **ON DELETE CASCADE**: Esta restricción asegura que si un grupo se elimina de la 
tabla Grupo, todos los integrantes asociados a ese grupo también sean eliminados 
automáticamente de la tabla Integrante_Grupo. Esto previene la existencia de 
registros huérfanos en la tabla Integrante_Grupo, es decir, integrantes que pertenecen 
a un grupo que ya no existe.
* **ON UPDATE CASCADE**: Esta restricción garantiza que si se actualiza el IDGrupo 
en la tabla Grupo, los registros correspondientes en la tabla Integrante_Grupo se 
actualicen automáticamente para reflejar ese cambio. Esto mantiene la consistencia 
entre ambas tablas, evitando que los integrantes sigan haciendo referencia a un 
IDGrupo desactualizado. 
