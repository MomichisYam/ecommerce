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
