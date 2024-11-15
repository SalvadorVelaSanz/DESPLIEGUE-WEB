# Práctica 3.2: Despliegue de aplicaciones con Node Express

## Introducción

En esta práctica vamos a realizar el despliegue de aplicaciones Node.js sobre un servidor Node Express. Lo curioso de este caso es que el despliegue aquí cambia un poco puesto que no se hace sobre el servidor, sino que la aplicación es el servidor.

> **Warning**
>
> Comprueba que el servidor Tomcat de prácticas anteriores no está corriendo o nos dará problemas:
>
> ```bash
> sudo systemctl status tomcat9
> ```
>
> Y en caso de salir activo, pararlo:
>
> ```bash
> sudo systemctl stop tomcat9
> ```

Si no lo has instalado mediante APT, deberás ir al directorio donde lo tengas. En mi caso es `/opt/tomcat` y hacer:

```bash
cd /opt/tomcat/bin
./shutdown.sh
```
![Captura 1](images/Practica3.2/1/1.png)

## Instalación de Node.js, Express y test de la primera aplicación

La primera parte de la práctica es muy sencilla. Consistirá en instalar sobre nuestra Debian 11 tanto Node.js como Express y tras ello crear un archivo `.js` de prueba para comprobar que nuestro primer despliegue funciona correctamente.

Para ello, os podéis apoyar en este sencillo tutorial o este otro, Y para Express:

En lugar de acceder a `http://localhost:3000`, debéis acceder desde vuestra máquina local a `http://IP-maq-virtual:3000`, utilizando la IP concreta de vuestra máquina virtual.

> **Recordatorio**
>
> Debéis añadir a vuestro grupo de seguridad el puerto que estéis utilizando para acceder a la aplicación (3000 u otro), permitiendo el tráfico de entrada hacia ese puerto TCP.
>
> Recordad parar el servidor (`CTRL+C`) al acabar la práctica.

## Task

Documenta, incluyendo capturas de pantallas, el proceso que has seguido para realizar el despliegue de esta nueva aplicación, así como el resultado final.

## Instalación de Node.js y Express en Debian 11

Para comenzar, abre una terminal y actualiza el sistema operativo:

```bash
sudo apt update
sudo apt upgrade
```
![Captura 2](images/Practica3.2/1/2.png)

Luego, añade el repositorio de la rama 16.x de NodeJS:

```bash
curl -sL https://deb.nodesource.com/setup_16.x | sudo -E bash -
```
![Captura 3](images/Practica3.2/1/3.png)

Después, ejecuta el siguiente comando:

```bash
sudo apt install nodejs
```
![Captura 4](images/Practica3.2/1/4.png)

Finalmente, verifica las versiones instaladas de NodeJS y NPM para asegurarte de que la instalación fue exitosa:

```bash
node --version
v16.13.2
npm --version
8.1.2
```
![Captura 5](images/Practica3.2/1/5.png)

### Instalando ExpressJS en Debian 11

Ahora es momento de instalar Express.js. Para hacerlo de manera global, ejecuta:

```bash
sudo npm install -g express
```
![Captura 6](images/Practica3.2/1/6.png)

#### 1. Instalando ExpressJS en Debian 11

Primero, crea una carpeta para el proyecto:

```bash
mkdir project
```

Accede a la carpeta:

```bash
cd project
```

Inicializa el proyecto:

```bash
npm init -y
```
![Captura 7](images/Practica3.2/1/7.png)

Instala Express.js localmente para este proyecto:

```bash
npm install express
```

Crea un archivo de ejemplo:

```bash
sudo nano app.js
```
![Captura 8](images/Practica3.2/1/8.png)

Agrega el siguiente contenido:

```javascript
const express = require('express')
const app = express()
const port = 3000

app.get('/', (req, res) => {
    res.send('Hola. Bienvenido a este blog')
})

app.listen(port, () => {
    console.log(`Aplicación de ejemplo escuchando en http://localhost:${port}`)
})
```
![Captura 9](images/Practica3.2/1/9.png)

#### 2. Creando una nueva aplicación con Express.js

Guarda los cambios y cierra el editor.

Ejecuta el proyecto con este comando:

```bash
node app.js
```

Salida de ejemplo:

```bash
Aplicación de ejemplo escuchando en http://localhost:3000
```
![Captura 10](images/Practica3.2/1/10.png)
![Captura 11](images/Practica3.2/1/11.png)

## Despliegue de una nueva aplicación

Vamos ahora a realizar el despliegue de una aplicación de terceros para ver cómo es el proceso.

Se trata de un "prototipo" de una aplicación de predicción meteorológica que podéis encontrar en este repositorio de Github.

Tal y como indican las instrucciones del propio repositorio, los pasos a seguir son, en primer lugar, clonar el repositorio a nuestra máquina:

```bash
git clone https://github.com/MehedilslamRipon/Shopping-Cart-Application
```

Movernos al nuevo directorio:

```bash
cd Shopping-Cart-Application/
```

Instalar las librerías necesarias (paciencia, este proceso puede tardar un buen rato):

```bash
npm install
```
![Captura 12](images/Practica3.2/1/12.png)

Y, por último, iniciar la aplicación:

```bash
npm run start
```

Cuando sigáis el proceso necesario e intentéis iniciar la aplicación con Express, os dará un error del tipo:

```bash
sh: 1: nodemon: not found
```
![Captura 13](images/Practica3.2/1/13.png)

Este error ocurre porque no tenemos instalado el nodemon. para arreglarlo podemos instalarlo globalmente o solo en el proyecto. en mi caso lo hare en el proyecto

para eso tenemos que usar el siguiente comando dentro del proyecto:

```bash
npm install nodemon --save-dev
```
![Captura 14](images/Practica3.2/1/14.png)
![Captura 15](images/Practica3.2/1/15.png)
