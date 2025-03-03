# Tabla de artista 

La entidad de artista es dónde se almacenarán todos los datos de los artístas, pero, de acuerdo al  
esquema relacional, esta tabla solo debe tener 2 columnas, ya que un artista puede dividirse en  
2 tipos de artistas, **Artistas individuales** y **Artistas grupales** 

## Columnas de artista 

* **ID**:  Un campo de tipo INT que se autoincrementa automáticamente cada vez que se  
inserta un nuevo registro. Además, está marcado como la clave primaria (PRIMARY  
KEY), lo que garantiza que cada valor de ID sea único en la tabla.
* **Nombre**:  Un campo de tipo VARCHAR(255) que almacena el nombre del artista y   
no puede ser NULL (es decir, debe contener un valor).

### Ejemplo 

| ID | Nombre |
|-|-|
| 6 | Fulanito |
