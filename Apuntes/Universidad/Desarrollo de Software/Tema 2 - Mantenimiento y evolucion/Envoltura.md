Tambien conocido como *wrap*
Es una **alternativa al mantenimiento**. Programa que recibe los mensajes desde el programa cliente y transforma la entrada en una representación que puede enviar al sistema heredado
- **Interfaz externa**. Generalmente, paso de mensajes de cadenas ASCII
- **Interfaz interna**. Hay que especificar el lenguaje del software heredado
- **Gestor de mensajes**. Buffers de entrada y salida de mensajes para almacenar los datos que necesitan esperar dadas las distintas velocidades de procesamiento del cliente y del objetivo
- **Convertidor de interfaces**. Se encarga de cambiar los parámetros necesarios para adaptarlos a cada una de las interfaces
- **Emulador E/S**. Intercepta las E/S del software heredado y pone la información en el buffer correspondiente
![[Pasted image 20240416165441.png]]