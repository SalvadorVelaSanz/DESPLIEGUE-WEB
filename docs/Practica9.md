# Práctica 4.1 - Configuración de un servidor DNS

## Instalación de servidor DNS

Bind es el estándar de facto para servidores DNS. Es una herramienta de software libre y se distribuye con la mayoría de plataformas Unix y Linux, donde también se le conoce con el sobrenombre de named (name daemon). Bind9 es la versión recomendada para usarse y es la que emplearemos.

Para instalar el servidor DNS en Ubuntu Server, usaremos los repositorios oficiales. Por ello, podremos instalarlo como cualquier paquete en Ubuntu:

```bash
sudo apt-get install bind9 bind9utils bind9-doc
```
![Captura 1](images/Practica4.1/1.png)

## Configuración del servidor

Puesto que en clase sólo vamos a utilizar IPv4, vamos a decírselo a Bind, en su archivo general de configuración. Este archivo named se encuentra en el directorio:

`/etc/default`
![Captura 2](images/Practica4.1/2.png)

Y para indicarle que sólo use IPv4, debemos modificar la línea siguiente con el texto resaltado:

```plaintext
OPTIONS = "-u bind -4"
```
![Captura 3](images/Practica4.1/3.png)

El archivo de configuración principal named.conf de Bind está en el directorio:

`/etc/bind`
![Captura 4](images/Practica4.1/4.png)

Si lo consultamos veremos lo siguiente:

![Captura 5](images/Practica4.1/5.png)

Este archivo sirve simplemente para aglutinar o agrupar a los archivos de configuración que usaremos. Estos 3 includes hacen referencia a los 3 diferentes archivos donde deberemos realizar la verdadera configuración, ubicados en el mismo directorio.

### Configuración named.conf.options

Es una buena práctica que hagáis siempre una copia de seguridad de un archivo de configuración cada vez que vayáis a realizar algún cambio:

```bash
sudo cp /etc/bind/named.conf.options /etc/bind/named.conf.options.backup
```
![Captura 6](images/Practica4.1/6.png)

Ahora editaremos el archivo named.conf.options e incluiremos los siguientes contenidos:

Por motivos de seguridad, vamos a incluir una lista de acceso para que sólo puedan hacer consultas recursivas al servidor aquellos hosts que nosotros decidamos.

En nuestro caso, los hosts confiables serán los de la red 192.168.X.0/24 (donde la X depende de vuestra red de casa). Así pues, justo antes del bloque `options {…}`, al principio del archivo, añadiremos algo así:

![Captura 7](images/Practica4.1/7.png)

Si nos fijamos el servidor por defecto ya viene configurado para ser un DNS caché. El directorio donde se cachearán o guardarán las zonas es `/var/cache/bind`.

- Que sólo se permitan las consultas recursivas a los hosts que hemos decidido en la lista de acceso anterior.
- No permitir transferencia de zonas a nadie, de momento.
- Configurar el servidor para que escuche consultas DNS en el puerto 53 (por defecto DNS utiliza puerto 53 UDP) y en la IP de su interfaz de la red privada. Deberéis colocar la IP de la interfaz de vuestra Debian, puesto que resolverá las consultas DNS del cliente/s de esa red.
- Permitir las consultas recursivas, ya que en el primer punto ya le hemos dicho que sólo puedan hacerlas los hosts de la ACL.

Además, vamos a comentar la línea que pone `listen-on-v6 { any; };` puesto que no vamos a responder a consultas de IPv6. Para comentarla basta añadir al principio de la línea dos barras `//`. También podría hacerse con una almohadilla pero aparecería resaltado con color ya que estos comentarios los suele utilizar el administrador para aclarar algún aspecto de la configuración.

![Captura 8](images/Practica4.1/8.png)

Podemos comprobar si nuestra configuración es correcta con el comando:

```bash
sudo named-checkconf
```

Si hay algún error, nos lo hará saber. En caso contrario, nos devuelve a la línea de comandos.

Reiniciamos el servidor y comprobamos su estado:

```bash
sudo systemctl restart bind9
sudo systemctl status bind9
```
![Captura 9](images/Practica4.1/9.png)

### Configuración named.conf.local

En este archivo configuraremos aspectos relativos a nuestras zonas. Vamos a declarar la zona “deaw.es”. Por ahora simplemente indicaremos que el servidor DNS es maestro para esta zona y donde estará ubicado el archivo de zona que crearemos más adelante:

![Captura 10](images/Practica4.1/10.png)

### Creación del archivo de zona

Vamos a crear el archivo de zona de resolución directa justo en el directorio que hemos indicado antes y con el mismo nombre que hemos indicado antes.

![Captura 11](images/Practica4.1/11.png)

El contenido será algo así (procurad respetar el formato):

![Captura 12](images/Practica4.1/12.png)

### Creación del archivo de zona para la resolución inversa

Recordad que deben existir ambos archivos de zona, uno para la resolución directa y otro para la inversa. Vamos pues a crear el archivo de zona inversa.

En primer lugar, debemos añadir las líneas correspondientes a esta zona inversa en el archivo named.conf.local, igual que hemos hecho antes con la zona de resolución directa:

![Captura 13](images/Practica4.1/13.png)

Donde la X es el tercer byte de vuestra red.

Y la configuración de la zona de resolución inversa:

![Captura 14](images/Practica4.1/14.png)
![Captura 15](images/Practica4.1/15.png)

Podemos comprobar que la configuración de las zonas es correcta con el comando adecuado.

### Comprobación de las configuraciones

Para comprobar la configuración de la zona de resolución directa:

```bash
sudo named-checkzone deaw.es /etc/bind/db.deaw.es
```

Y para comprobar la configuración de la zona de resolución inversa:

```bash
sudo named-checkzone X.168.192.in-addr.arpa /etc/bind/db.X.168.192
```

Si todo está bien, devolverá OK. En caso de haber algún error, nos informará de ello.

![Captura 16](images/Practica4.1/16.png)

Reiniciamos el servicio y comprobamos el estado:

```bash
sudo systemctl restart bind9
sudo systemctl status bind9
```
![Captura 17](images/Practica4.1/17.png)

## Atención

Es muy importante que el cliente esté configurado para usar como servidor DNS el que acabamos de instalar y configurar. Ya sea Windows, ya sea Linux, debéis cambiar vuestra configuración de red para que la máquina con la que hagáis las pruebas utilice este servidor DNS como el principal.

![Captura 18](images/Practica4.1/18.png)

## Comprobación de las resoluciones y de las consultas

Podemos comprobar desde los clientes, con `dig` o `nslookup` las resoluciones directas e inversas.

![Captura 19](images/Practica4.1/19.png)

## Cuestiones finales

### Cuestión 1

¿Qué pasará si un cliente de una red diferente a la tuya intenta hacer uso de tu DNS de alguna manera, le funcionará? ¿Por qué, en qué parte de la configuración puede verse?

### Cuestión 2

¿Por qué tenemos que permitir las consultas recursivas en la configuración?

### Cuestión 3

El servidor DNS que acabáis de montar, ¿es autoritativo? ¿Por qué?

### Cuestión 4

¿Dónde podemos encontrar la directiva $ORIGIN y para qué sirve?

### Cuestión 5

¿Una zona es idéntico a un dominio?

### Cuestión 6

¿Pueden editarse los archivos de zona de un servidor esclavo/secundario?

### Cuestión 7

¿Por qué podría querer tener más de un servidor esclavo para una misma zona?

### Cuestión 8

¿Cuántos servidores raíz existen?

### Cuestión 9

¿Qué es una consulta iterativa de referencia?

### Cuestión 10

En una resolución inversa, ¿a qué nombre se mapearía la dirección IP 172.16.34.56?
