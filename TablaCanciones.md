# Tabla de canciones

La tabla de canciones es donde se almacena la principal entidad de la base de datos, las canciones, estas poseen otra tabla de  
nombre género que relaciona su género con otra tabla, además de relacionarse con un álbum y artista 1 o 2.

## Columnas de canción

* **ID**: Un campo INT que se autoincrementa y actúa como la clave primaria (PRIMARY 
KEY) de la tabla. 
* **Titulo**: Un campo VARCHAR(255) que no puede ser NULL y almacena el título de 
la canción. 
* **Descripcion**: Un campo de tipo TEXT que es opcional (NULL por defecto) y puede 
almacenar una descripción de la canción. 
* **Duracion**: Un campo de tipo TIME que no puede ser NULL y almacena la duración 
de la canción. 
* **IDArtista1**: Un campo INT que es obligatorio (NOT NULL) y se refiere al ID del 
primer artista de la canción. 
* **IDArtista2**: Un campo INT que puede ser NULL y se refiere al ID del segundo artista 
(en caso de ser una colaboración entre dos artistas). 
* **IDAlbum**: Un campo INT que puede ser NULL y se refiere al ID del álbum donde 
está incluida la canción. Si la canción no pertenece a un álbum, este campo se deja 
NULL.
### Ejemplo 

| IDCancion | Titulo | Duración | IDArtista | IDAlbum |
|-|-|-|-|-|
| 6 | 365 | 05:15 | 9 | 10 |

## Relaciones de llaves foráneas 

* **FOREIGN KEY (IDArtista1) REFERENCES Artista(ID) ON DELETE 
CASCADE ON UPDATE CASCADE**: La clave foránea IDArtista1 se refiere al ID 
de la tabla Artista. Si se elimina un artista, se eliminarán todas las canciones asociadas 
a ese artista. Si se actualiza el ID de un artista, se actualizará automáticamente en las 
canciones relacionadas. 
* **FOREIGN KEY (IDArtista2) REFERENCES Artista(ID) ON DELETE 
CASCADE ON UPDATE CASCADE**: Similar a la anterior, pero para el segundo 
artista (en caso de existir). 
* **FOREIGN KEY (IDAlbum) REFERENCES Album(ID) ON DELETE 
CASCADE ON UPDATE CASCADE**: La clave foránea IDAlbum se refiere al ID 
de la tabla Album. Si se elimina un álbum, todas las canciones asociadas a ese álbum 
serán eliminadas. Si se actualiza el ID de un álbum, se actualizará automáticamente 
en las canciones. 

## Restricción de unicidad 

* **UNIQUE (Titulo, IDArtista1, IDAlbum)**: Asegura que no pueda haber dos 
canciones con el mismo título, mismo IDArtista1 y mismo IDAlbum. Esto es útil si 
un artista tiene múltiples canciones en un álbum, pero no se pueden repetir canciones 
con el mismo título en el mismo álbum para el mismo artista.
