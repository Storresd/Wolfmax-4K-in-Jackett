Buenas, tuve bastantes problemas para añadir diferentes indexadores en Jackett, pero tras investigar y consultar con la IA, conseguí crear un contenedor docker proxy para vincularlo con Jackett y así poder hacer que se pueda comunicar con las web sin problemas.

<img width="889" height="446" alt="image" src="https://github.com/user-attachments/assets/6a5ec3db-3eac-4d63-887a-da4e2834ae4b" />

Lo que tendremos que hacer, es desplegar un contenedor docket usando la imagen Gluetun (es un contenedor open source que hace de cliente VPN y trae de serie un servidor proxy SOCKS5 (y también HTTP) integrado, compatible directamente con ProtonVPN entre otros muchos proveedores).
En mi caso estoy utilizando la versión gratuita de ProtonVPN. Una vez nos creamos una cuenta nos dirigimos a las siguientes opciones para configurarlo con un servidor proxy:

<img width="1635" height="654" alt="image" src="https://github.com/user-attachments/assets/b6c7a1dd-14b5-4a18-8ffe-87d0bb93b3b9" />
En primera instancia aparecerá Download.

Una vez entrado en ese apartado, escribiremos un nombre, seleccionamos la opción Enrutador y Crear.

<img width="1236" height="867" alt="image" src="https://github.com/user-attachments/assets/9011363b-0fc9-416f-9b7e-9d171ec1e956" />

Una vez creado, descargamos el archivo que se nos genera:

<img width="598" height="623" alt="image" src="https://github.com/user-attachments/assets/c33bf0b7-8bb9-4dd8-ae52-2542ba35f59f" />

Con la información de dicho archivo podemos rellenar el archivo docker proporcionado y desplegarlo.

Una vez iniciado, nos dirigimos a nuestro Jackett, rellenamos la información del siguiente apartado:

<img width="762" height="826" alt="image" src="https://github.com/user-attachments/assets/55c52e61-8566-402c-b729-9423e70d2c7a" />

En caso de dar fallo con la opción SOCKS5 (1080), probamos con el HTTP (8888).
Luego añadimos indexadores y comprobamos si se han añadido correctamente.

Espero que os haya servido de utilidad.
