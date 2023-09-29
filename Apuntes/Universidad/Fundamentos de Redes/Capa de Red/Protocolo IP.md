## IPv4
- Especificado en el RFC 791

### Características IP:
?
- Protocolo para la *interconexión* de redes (subredes)
- Resuelve el *encaminamiento* en internet
- Es un protocolo *salto a salto*, involucra hosts y routers
- Ofrece un servicio *no orientado a conexión no fiable*
	```ad-seealso
	- No hay negociación, no existe una conexión lógica entre entidades
	- No existe control de errores, ni control de flujo, ni control de congestión
	- Funciona como el sistema de correo tradicional
	```
- La unidad de datos de IP se denomina *DATAGRAMA=cabecera+datos*
- IP es un protocolo de "buena voluntad" ("best effort"), los datagramas se pueden perder, duplicar, retrasar, desordenar...
- IP Gestiona la *fragmentación*, adapta el tamaño del datagrama a las diferente *Maximun Transfer Unit (MTUs)* de las distintas subredes necesarias hasta llegar al destino