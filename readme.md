## Configura un contenedor con la imagen oficial de bind9 utilizando docker-compose.
![alt text](<imagenes/Captura de pantalla 2024-04-26 182351.png>)
 
 Para crear un contenedor con un docker compose , lo priemro que debemos hacer es crear el archivo con la extension .yml y posteriormente escribir en el la configuracion deseada y lo ejecutaremos usando el comando docker compose up .

## Utiliza los volumenes tal como lo explica en el setup de la imagen
![alt text](<imagenes/Captura de pantalla 2024-04-26 183057.png>)

## descripción de las opciones del docker-compose.yml

<b></b> container_name:Especifica el nombre del contenedor como "asir_bind9".
image: Indica la imagen Docker utilizada para crear el contenedor. En este caso, se está utilizando la imagen ubuntu/bind9.

<b>platform:</b> Define la plataforma para la cual se va a construir la imagen. En este caso, se especifica linux/amd64, lo que indica que la imagen se construirá para arquitecturas de 64 bits en sistemas Linux.

<b>ports:</b> Mapea los puertos del contenedor al host. En este caso, el puerto 53 del contenedor (utilizado para servicios DNS) se mapea al puerto 53 del host.

<b>networks:</b> Define la configuración de red para el contenedor. Se crea una red llamada bind9_subnet, y se asigna la dirección IPv4 172.28.5.1 al contenedor dentro de esta red.

<b>volumes: </b>Especifica los volúmenes que se montarán en el contenedor. En este caso, se montan dos volúmenes:
./conf:/etc/bind: Monta el directorio local conf en /etc/bind dentro del contenedor. Esto se utiliza para proporcionar la configuración del servidor BIND9.

./zonas:/var/lib/bind: Monta el directorio local zonas en /var/lib/bind dentro del contenedor. Esto se utiliza para proporcionar las zonas de DNS que el servidor BIND9 va a servir.


