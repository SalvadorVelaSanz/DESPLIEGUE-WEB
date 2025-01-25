# GITHUB I

## Repositorio DEAW

1. Crear un repositorio en vuestro GitHub llamado DEAW.
2. Clonar vuestro repositorio en local.

![Captura 1](images/Practica5.1/Parte1/1.png)
![Captura 2](images/Practica5.1/Parte1/2.png)

## README

1. Crear (si no lo habéis creado ya) en vuestro repositorio local un documento `README.md`.
2. Escribir un pequeño texto en este README a propósito del repositorio y el módulo para el que se utilizará.

![Captura 3](images/Practica5.1/Parte1/3.png)


## Commit inicial, Push inicial

1. Realizar un commit inicial con el comentario `Comenzamos con los ejercicios de Git`.
2. Subir los cambios al repositorio remoto.

![Captura 4](images/Practica5.1/Parte1/4.png)

## Ignorar archivos

1. Crear en el repositorio local un fichero llamado `privado.txt`.
2. Crear en el repositorio local una carpeta llamada `privada`.
3. Realizar los cambios oportunos para que tanto el archivo como la carpeta sean ignorados por git.

![Captura 5](images/Practica5.1/Parte1/5.png)
![Captura 6](images/Practica5.1/Parte1/6.png)

## Añadir fichero `1.txt`

1. Añadir fichero `1.txt` al repositorio local.

## Crear el tag `v0.1`

1. Crear un tag `v0.1`.
2. Subir los cambios al repositorio remoto.

![Captura 7](images/Practica5.1/Parte1/7.png)

## Crear una rama `v0.2`

1. Crear una rama `v0.2`.
2. Posiciona tu carpeta de trabajo en esta rama.

## Añadir fichero `2.txt`

1. Añadir un fichero `2.txt` en la rama `v0.2`.


## Crear rama remota `v0.2`

1. Subir los cambios al repositorio remoto.

![Captura 8](images/Practica5.1/Parte1/8.png)

## Merge directo

1. Posicionarse en la rama `master`.
2. Hacer un merge de la rama `v0.2` en la rama `master`.

![Captura 9](images/Practica5.1/Parte1/9.png)

## Merge con conflicto

1. En la rama `master` poner `Hola` en el fichero `1.txt` y hacer commit.
2. Posicionarse en la rama `v0.2` y poner `Adios` en el fichero `1.txt` y hacer commit.
3. Posicionarse de nuevo en la rama `master` y hacer un merge con la rama `v0.2`.

![Captura 10](images/Practica5.1/Parte1/10.png)

## Listado de ramas

1. Listar las ramas con merge y las ramas sin merge.

![Captura 11](images/Practica5.1/Parte1/11.png)

## Arreglar conflicto

1. Arreglar el conflicto anterior y hacer un commit.

![Captura 12](images/Practica5.1/Parte1/12.png)
![Captura 13](images/Practica5.1/Parte1/13.png)

## Borrar rama

1. Crear un tag `v0.2`.
2. Borrar la rama `v0.2`.

![Captura 14](images/Practica5.1/Parte1/14.png)

## Listado de cambios

1. Listar los distintos commits con sus ramas y sus tags.

![Captura 14](images/Practica5.1/Parte1/15.png)


# GITHUB II



## Ejercicios de creación y actualización de repositorios

### Ejercicio 1
Configurar Git definiendo el nombre del usuario, el correo electrónico y activar el coloreado de la salida.

Mostrar la configuración final.

![Captura 1](images/Practica5.1/Parte2/1.png)

### Ejercicio 2
Crear un repositorio nuevo con el nombre libro y mostrar su contenido.

![Captura 2](images/Practica5.1/Parte2/2.png)


### Ejercicio 3
Comprobar el estado del repositorio.

Crear un fichero `indice.txt` con el siguiente contenido:

```
Capítulo 1: Introducción a Git
Capítulo 2: Flujo de trabajo básico
Capítulo 3: Repositorios remotos
```

Comprobar de nuevo el estado del repositorio.

Añadir el fichero a la zona de intercambio temporal.

Volver a comprobar una vez más el estado del repositorio.

![Captura 3](images/Practica5.1/Parte2/3.png)


### Ejercicio 4
Realizar un commit de los últimos cambios con el mensaje “Añadido índice del libro.” y ver el estado del repositorio.

![Captura 4](images/Practica5.1/Parte2/4.png)


### Ejercicio 5
Cambiar el fichero `indice.txt` para que contenga lo siguiente:

```
Capítulo 1: Introducción a Git
Capítulo 2: Flujo de trabajo básico
Capítulo 3: Gestión de ramas
Capítulo 4: Repositorios remotos
```

Mostrar los cambios con respecto a la última versión guardada en el repositorio.

Hacer un commit de los cambios con el mensaje “Añadido capítulo 3 sobre gestión de ramas”.

![Captura 5](images/Practica5.1/Parte2/5.png)


### Ejercicio 6
Mostrar los cambios de la última versión del repositorio con respecto a la anterior.

Cambiar el mensaje del último commit por “Añadido capítulo 3 sobre gestión de ramas al índice.”

Volver a mostrar los últimos cambios del repositorio.

![Captura 6](images/Practica5.1/Parte2/6.png)


## Ejercicios de manejo del historial de cambios

### Ejercicio 1
Mostrar el historial de cambios del repositorio.

Crear la carpeta `capitulos` y crear dentro de ella el fichero `capitulo1.txt` con el siguiente texto.

```
Git es un sistema de control de versiones ideado por Linus Torvalds.
```

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit de los cambios con el mensaje “Añadido capítulo 1.” Volver a mostrar el historial de cambios del repositorio.

![Captura 7](images/Practica5.1/Parte2/7.png)


### Ejercicio 2
Crear el fichero `capitulo2.txt` en la carpeta `capitulos` con el siguiente texto.

```
El flujo de trabajo básico con Git consiste en: 
1- Hacer cambios en el repositorio. 
2- Añadir los cambios a la zona de intercambio temporal. 
3- Hacer un commit de los cambios.
```

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit de los cambios con el mensaje “Añadido capítulo 2.”

Mostrar las diferencias entre la última versión y dos versiones anteriores.

![Captura 8](images/Practica5.1/Parte2/8.png)


### Ejercicio 3
Crear el fichero `capitulo3.txt` en la carpeta `capitulos` con el siguiente texto.

```
Git permite la creación de ramas lo que permite tener distintas versiones del mismo proyecto y trabajar de manera simultanea en ellas.
```

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit de los cambios con el mensaje “Añadido capítulo 3.”

Mostrar las diferencias entre la primera y la última versión del repositorio.

![Captura 9](images/Practica5.1/Parte2/9.png)

### Ejercicio 4
Añadir al final del fichero `indice.txt` la siguiente línea:

```
Capítulo 5: Conceptos avanzados
```

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit de los cambios con el mensaje “Añadido capítulo 5 al índice.”

Mostrar quién ha hecho cambios sobre el fichero `indice.txt`.
![Captura 10](images/Practica5.1/Parte2/10.png)


## Ejercicios de deshacer cambios

### Ejercicio 1
Eliminar la última línea del fichero `indice.txt` y guardarlo.

Comprobar el estado del repositorio.

Deshacer los cambios realizados en el fichero `indice.txt` para volver a la versión anterior del fichero.

Volver a comprobar el estado del repositorio.
![Captura 11](images/Practica5.1/Parte2/11.png)


### Ejercicio 2
Eliminar la última línea del fichero `indice.txt` y guardarlo.

Añadir los cambios a la zona de intercambio temporal.

Comprobar de nuevo el estado del repositorio.

Quitar los cambios de la zona de intercambio temporal, pero mantenerlos en el directorio de trabajo.

Comprobar de nuevo el estado del repositorio.

Deshacer los cambios realizados en el fichero `indice.txt` para volver a la versión anterior del fichero.

Volver a comprobar el estado del repositorio.
![Captura 12](images/Practica5.1/Parte2/12.png)

### Ejercicio 3
Eliminar la última línea del fichero `indice.txt` y guardarlo.

Eliminar el fichero `capitulos/capitulo3.txt`.

Añadir un fichero nuevo `capitulos/capitulo4.txt` vacío.

Añadir los cambios a la zona de intercambio temporal.

Comprobar de nuevo el estado del repositorio.

Quitar los cambios de la zona de intercambio temporal, pero mantenerlos en el directorio de trabajo.

Comprobar de nuevo el estado del repositorio.

Deshacer los cambios realizados para volver a la versión del repositorio.

Volver a comprobar el estado del repositorio.

![Captura 13](images/Practica5.1/Parte2/13.png)
![Captura 14](images/Practica5.1/Parte2/14.png)

### Ejercicio 4
Eliminar la última línea del fichero `indice.txt` y guardarlo.

Eliminar el fichero `capitulos/capitulo3.txt`.

Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “Borrado accidental.”

Comprobar el historial del repositorio.

Deshacer el último commit pero mantener los cambios anteriores en el directorio de trabajo y la zona de intercambio temporal.

Comprobar el historial y el estado del repositorio.

Volver a hacer el commit con el mismo mensaje de antes.

Deshacer el último commit y los cambios anteriores del directorio de trabajo volviendo a la versión anterior del repositorio.

Comprobar de nuevo el historial y el estado del repositorio.
![Captura 15](images/Practica5.1/Parte2/15.png)
![Captura 16](images/Practica5.1/Parte2/16.png)

## Ejercicios de gestión de ramas

### Ejercicio 1
Crear una nueva rama `bibliografia` y mostrar las ramas del repositorio.

![Captura 17](images/Practica5.1/Parte2/17.png)

### Ejercicio 2
Crear el fichero `capitulos/capitulo4.txt` y añadir el texto siguiente:

```
En este capítulo veremos cómo usar GitHub para alojar repositorios en remoto.
```

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit con el mensaje “Añadido capítulo 4.”

Mostrar la historia del repositorio incluyendo todas las ramas.

![Captura 18](images/Practica5.1/Parte2/18.png)

### Ejercicio 3
Cambiar a la rama `bibliografia`.

Crear el fichero `bibliografia.txt` y añadir la siguiente referencia:

```
Chacon, S. and Straub, B. Pro Git. Apress.
```

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit con el mensaje “Añadida primera referencia bibliográfica.”

Mostrar la historia del repositorio incluyendo todas las ramas.

![Captura 19](images/Practica5.1/Parte2/19.png)


### Ejercicio 4
Fusionar la rama `bibliografia` con la rama `master`.

Mostrar la historia del repositorio incluyendo todas las ramas.

Eliminar la rama `bibliografia`.

Mostrar de nuevo la historia del repositorio incluyendo todas las ramas.

![Captura 20](images/Practica5.1/Parte2/20.png)

### Ejercicio 5
Crear la rama `bibliografia`.

Cambiar a la rama `bibliografia`.

Cambiar el fichero `bibliografia.txt` para que contenga las siguientes referencias:

```
Scott Chacon and Ben Straub. Pro Git. Apress.
Ryan Hodson. Ry’s Git Tutorial. Smashwords (2014)
```

Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “Añadida nueva referencia bibliográfica.”

Cambiar a la rama `master`.

Cambiar el fichero `bibliografia.txt` para que contenga las siguientes referencias:

```
Chacon, S. and Straub, B. Pro Git. Apress.
Loeliger, J. and McCullough, M. Version control with Git. O’Reilly.
```

Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “Añadida nueva referencia bibliográfica.”

Fusionar la rama `bibliografia` con la rama `master`.

Resolver el conflicto dejando el fichero `bibliografia.txt` con las referencias:

```
Chacon, S. and Straub, B. Pro Git. Apress.
Loeliger, J. and McCullough, M. Version control with Git. O’Reilly.
Hodson, R. Ry’s Git Tutorial. Smashwords (2014)
```

Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “Resuelto conflicto de bibliografía.”

Mostrar la historia del repositorio incluyendo todas las ramas.

![Captura 21](images/Practica5.1/Parte2/21.png)
![Captura 22](images/Practica5.1/Parte2/22.png)
![Captura 23](images/Practica5.1/Parte2/23.png)

## Ejercicios de repositorios remotos

### Ejercicio 1
Crear un nuevo repositorio público en GitHub con el nombre `libro-git`.

Añadirlo al repositorio local del libro.

Mostrar todos los repositorios remotos configurados.

![Captura 24](images/Practica5.1/Parte2/24.png)
![Captura 25](images/Practica5.1/Parte2/25.png)

### Ejercicio 2
Añadir los cambios del repositorio local al repositorio remoto de GitHub.

Acceder a GitHub y comprobar que se han subido los cambios mostrando el historial de versiones.

![Captura 26](images/Practica5.1/Parte2/26.png)
![Captura 30](images/Practica5.1/Parte2/30.png)

### Ejercicio 3
Colaborar en el repositorio remoto `libro-git` de otro usuario.

Clonar su repositorio `libro-git`.

Añadir el fichero `autores.txt` que contenga el nombre del usuario y su correo electrónico.

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit con el mensaje “Añadido autor.”

Subir los cambios al repositorio remoto.

![Captura 27](images/Practica5.1/Parte2/27.png)
![Captura 28](images/Practica5.1/Parte2/28.png)
![Captura 29](images/Practica5.1/Parte2/29.png)

