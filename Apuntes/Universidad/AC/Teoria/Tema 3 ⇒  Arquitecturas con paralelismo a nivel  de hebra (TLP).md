- Arquitecturas con [TLP](../../../../TLP.md)
    - Clasificación y estructuras de arquitecturas con [TLP](../../../../TLP.md) explícito y una instancia del SO
        - Estructuras ↓ 
            - Multiprocesador→Ejecuta un flujo de instrucciones distintos en cada uno de los distintos procesadores/cores físicos de los que dispone el sistema.
            - Multicore ( __multinulcleo__ )→Ejecuta distintos flujos de intrucciones dentro de un mismo procesador con varios nucleos fisicos. Una thread para cada nucleo.
            - Núcleo ( __Core) multithread__ →Núcleo al que se le ha modificado su arquitectura [ILP](../../../../ILP.md) para ejecutar flujos de instrucciones en paralelo.
    - Multiprocesadores
        - Criterios de clasificación:
            1. **Sistema de memoria**
                - [NUMA](../../../../NUMA/NUMA.md) 
                    - Mayor latencia, poco escalable
                    - 
                - [UMA](../../../../UMA.md) 
                    - Menor latencia, mas escalabilidad pero una mayor dificultad a la hora de escribir el código.
                - ![](https://remnote-user-data.s3.amazonaws.com/Tn7Fw7g73W2pXTMoXBJUyXS66lac9c8VMPePTehtBtrBolA-iBuWcSz6VsfETAICzEJhm-DSDBvhoaH3pub3ENhNL8a475m446u7rjnF7G7vwbK3Hq_mNYbsefmT-T1d.png) 
            2. **Nivel de empaquetamiento:**
                - ![](https://remnote-user-data.s3.amazonaws.com/dzCMWMW68UUbIGcIuEiQBpK5xKYe1YvB2p_kvjxoBLdwVWg5CIsznxDWL6VGUWSSeUGcmraMa8I58Cky8rb7s9ZosI7smN0DQKAY2f9d9AV-4yIS2AMf4tj1Nx-ijrpS.png) 
    - Multicores 
        - Ejemplos Estructuras:
            - ![](https://remnote-user-data.s3.amazonaws.com/31SW4nXFqm0KySLhpNAkA1oEJMozbjM2bOpX2BqFAwMfM9Je_SixwirR4tPTiVxTyZXPcMnCVv-MzcsRpITEIYyyvf1HRtCkhoUhEtM02Seg1A3QTWy591en9BEPXex-.png) 
            - ![](https://remnote-user-data.s3.amazonaws.com/eXejJWQoy_du268t4vZcHH5xK2HF-iFr3LN1p3PfP_HLW80KJxIkQ91-eF9Or_LGXIbF3R-BUfDMj88x61zEC4xJ0bX1lqKYquSfwmxTL8NfTEgVRcgA1y2kbrrG80EW.png) 
        - 
- Coherencia del Sistema de Memoria
    - ![](https://remnote-user-data.s3.amazonaws.com/Mqz1KvbBk66kObngO3H2Lluax8A8XCs1vGKuWb41X8C3-CMdYJOSm6Yo-SKCWhS_rRte7m3sOAgqG-hf8vNdYoheaoaDYjyqweRtwLNH7qLZFmxi9P05NbJNtLnvDxZR.png) 
    1. Sistema de Memoria en multiprocesadores.
        - Que incluye? ↓ 
            - Cache para todos los nodos/cores
            - Memoria Principal
            - Controladores 
            - Buffers
            - Medio de comunicación de todos estos componentes (red de interconexión) 
        - La comunicación de datos entre procesadores la realiza el sistema de memoria
            - La lectura de una dirección de memoria debe devolver lo último que se ha escrito (desde el punto de vista de todos los componentes del sistema)
    2. Concepto de coherencia en el sistema de memoria. Situaciones de incoherencia y requisitos para evitar problemas en estos casos.
        - ![](https://remnote-user-data.s3.amazonaws.com/Vqg-Ns9A63j-4n4qr6mYHEeeRuBst2HbGNBRLGc7M77nsq3JZGzyDd96iHPxQwqYGySq7O1sBznzV8bC_cRXR_Nkw5VGqNHZWnrShi-fzKjZYx9S-YDsaax9PLuP4Fpu.png)
            - Métodos de actualización de memoria principal implementados en cache:
                - **Escritura Directa (write-through) **→** **Con este mecanismo no se permiten las situaciones de incoherencia entre la cache y la memoria principal ya que esta se actualiza tras cada modificación de una dirección en la cache.
                    - En aplicaciones ejecutadas en un computador, tras modificar una dirección de memoria en cache, se escribe al poco tiempo en memoria siguiendo los principios de  __localidad espacial y temporal. __ Esto genera un acceso continuo a memoria haciendo mas rentable reescribir el bloque completo donde se encuentra la dirección de memoria antes que solo esta. 
                - **Postescritura (write-back) **→Con este sistema, el bloque se escribe en memoria principal cuando se desaloja de la caché para dar espacio a un nuevo bloque. Evitando escrituras innecesarias en Memoria Principal. En cambio las copias de ese bloque en otras cachés si han de actualizarse a traves de algun protocolo de difusión.
                    - Lo mas usual es dotar al bloque de información de un bit de estado que identifique cuando una dirección ha sido actualizada para pedir la nueva copia a la caché mas actualizada.
        - Mecanismos de prevención de incoherencias entre cachés:
            - Para evitar una situación de incoherencia entre las cachés se deben de cumplir **2 CONDICIONES:**
                - **C1 Propagación de escritura **→** **Se debe garantizar que todo lo que se escribe en la copia de un bloque en una caché se propaga a las copias del bloque en otras cachés.
                - **C2 Serialización de escrituras **→** **Se debe garantizar que las escrituras en una dirección se ven en el mismo orden desde todos los procesadores (es decir, el sistema de memoria debe parecer que realiza las operaciones una detrás de otra de manera atómica).
        - Mecanismos de propagación de escrituras a otras cachés:
            - **Escritura con actualización (write-update)**→** **Cada vez que el procesador escribe en una dirección en su caché se escribe también en las copias de esa dirección en otras cachés. Si se cumplen los principio de localidad espacial  o temporal puede generar trafico innecesario.
            - **Escritura con invalidación (write-invalidation) **→** ** __Antes de que un procesador modifique una dirección de memoria se invalidan __ todas las copias del bloque que contiene esa dirección de memoria. Cuando eventualmente un núcleo quiere acceder a un bloque invalidado. Pide una copia a la caché mas actualizada o a memoria. Necesario incluir esta información en la información de estado del bloque.
            - La propagación en las escrituras se puede realizar:
                - Difusión a todas las caches del paquete que se va a modificar (los multiprocesadores UMA pueden llevar este mecanismo implementado por hardware a través de un bus especifico de copia de datos entre cachés)
                - Envío selectivo a las caches con la copia del bloque (implica almacenar mas información sobre que caché almacena que bloque de memoria)
    3. Protocolos de mantenimiento de la coherencia: Clasificación y diseño.
        - Protocolos de espionaje (snoopy).
            - Para buses, y en general sistemas con una difusión eficiente
        - Protocolos basados en directorios.
            - Para redes sin difusión o escalables(multietapa y estáticas).
        - Esquemas Jerárquicos.
            - Para redes jerárquicas
        - Protocolos de mantenimiento de coherencia.
            - **Políticas de actualización** ↓ 
                1. Escritura Directa
                2. Postescritura
                3. Mixto 
            - **Políticas de coherencia de caché/comportamiento** ↓ 
                1. Escritura con invalidación
                2. Escritura con actualización(inmediata)
                3. Mixta
            - **Descripción del comportamiento** ↓ 
                1. Posibles estados de un bloque en caché.
                2. Posibles estados de un bloque en memoria principal.
                3. Los paquetes que genera el controlador de la **caché**.
                4. Los paquetes que genera el controlador de la **memoria principal.**
                5. Definir las transiciones de estados para los bloques.
    4. Protocolo MSI de espionaje (Modified-Shared-Invalid).
        - Estados bloque en caché ↓ 
            1. **Modificado (M) ⇒** un bloque en este estado es la única copia del bloque de memoria en todo el sistema. El controlador debe responder con el bloque si le llega con el bus una peticion con lectura del bloque o escribirlo en memoria si se reemplaza por otro.
            2. **Compartido (C,S) ⇒** un bloque en este estado en caché es valido, también se encuentran copias de este bloque en otras cachés o en memoria principal. El controlador ha de invalidarlo si lee una petición de invalidación en el bus.
            3. **Invalido (I) ⇒** o bien el bloque se encuentra en la cache pero con información desactualizada o bien ya no se encuentra en caché. Cuando el procesador intenta acceder a este bloque se genera un fallo de caché y el controlador envía la petición pertinente por el bus.
        - Estados de un bloque en memoria ↓ 
            - **Válido ⇒ **el bloque está actualizado en memoria principal y puede haber una copia valida en varias cachés. El controlador responde con el bloque si ve en el bus una petición con lectura de un bloque con este estado.
            - **Inválido** ⇒ el bloque no está actualizado, existe una copia valida en una caché. 
        - Notación paquetes: 
            - Paquetes que genera un controlador de caché ↓ 
                - PtLect(B) ⇒ petición de lectura del paquete B (se genera tras un fallo de caché del nodo).
                - PtLectEx(B) ⇒ Petición de acceso exclusivo a un bloque con lectura. (se genera tras una petición de escritura del procesador cuando tiene una copia invalida del bloque en caché).
                - PtEx(B) ⇒ Petición de acceso exclusivo al bloque B. (Se genera por lo general tras una peticion de escritura sobre un bloque en estado compartido, como respuesta a este comando se invalidarian las copias del resto de cachés
                - PtPEsc(B) ⇒ Petición de posescritura de un bloque. Reemplazo de un bloque a estado modificado (se actualiza en MP)
                - RPBloque(B) ⇒ Respuesta con bloque. (Se genera cuando se tiene un bloque en estado modificado y se obtiene una peticion de lectura (exclusiva o no) del exterior. Alberga el bloque de memoria en su interior).
            - Paquetes que genera el controlador de Memoria 
                - Solo emite paquetes de respuesta ante peticiones de lectura Si y solo SI se almacena en memoria una copia valida del bloque. Siempre responde pasando una copia por el bus. Si un controlador de caché también responde a la petición el controlador que recibe la copia se encargará de discriminar la respuesta de MP.
        - Relación de acciones con eventos recibidos y estados. 
        - ![](https://remnote-user-data.s3.amazonaws.com/Qpi7IsPon_L4T_Bp6lflsRQG_Ojm79KhKU5jiWiQO0E75_SgYrvC3YUu-BcbGmFg7grFt4pk2MZlHGXK6IPHZGyX32T0sXULyEmW8BCUpbmsyUwbXnj1Sh3SpeLvWANs.png) 
    5. Protocolo MESI de espionaje. 
        - Siempre que con el protocolo MSI se escribe en la copia de un bloque en una caché se genera un paquete de petición con acceso exlusivo al bloque con el objetivo de invalidar el resto de copias. Esto genera trafico innecesario si solo existe una copia en la caché. 
        - El protocolo MESI separa el estado compartido en dos:
            - **Exclusivo (E) ⇒ **No hay copias del bloque B en otras cachés
            - **Compartido (S) ⇒ **Existe al menos otras copia del bloque B en otra caché. 
        - Se genera una nueva tabla de relación de acciones:
        - ![](https://remnote-user-data.s3.amazonaws.com/3n2xvunLvtrlOyrs2c_tM9xxn2PUhgYo6eTgC4yPhJ_cLHdv4EKZG146mujuiQTGt80Iz1cJGEOr92p8mUiQ5d1F328cAZjaN9dfAWdDHEj3APYWymHV59BVI7wu0Y8I.png) 
    6. Protocolo MSI basado en directorios con o sin difusión. 
        - Clasificación nodos cómputo:
            1. Nodo solicitante de un bloque (**S**) ⇒ Genera una petición de un bloque.
            2. Nodo origen de un bloque (**O**) ⇒ En un multiprocesador [NUMA](../../../../NUMA/NUMA.md)  la memoria está repartida físicamente, haciendo que una sección del espacio de direcciones esté más cerca físicamente que el resto. El nodo  __home __ de un bloque de memoria es aquel e el que se aloja físicamente le bloque. 
            3. Nodo propietario de un bloque (**P**) ⇒ Es un nodo que tiene una copia valida de un bloque en su caché.
        - Protocolo MSI para Multiprocesadores [NUMA](../../../../NUMA/NUMA.md) sin difusión:
            - Como no se usa difusión, ha de almacenarse en memoria principal, además del estado del bloque en memoria, información sobre las cachés con copia del bloque para que las invalidaciones se puedan propagar a los nodos con una copia valida del bloque.
            - 
- Consistencia del Sistema de Memoria
    - Consistencia de memoria→Especifica las restricciones en el orden en el cual las operaciones de memoria deben parecer haberse realizado.
    - Coherencia de memoria→Especifica las restricciones en el orden en el cual las operaciones sobre una dirección de memoria parecen haber sido realizadas.
    - Consistencia Secuencial: 
        - Es el modelo de consistencia que se suele usar en las herramientas de alto nivel.
        - Requiere de ↓ 
            - **Orden del programa**→Las operaciones de memoria que ejecuta cada flujo de instrucciones deben realizarse en el orden descrito por el código que ejecuta el flujo de instrucciones.
            - **Orden Global **o **atomicidad**→**  **Todas las instrucciones de memoria parezcan ser ejecutadas una cada vez ⇒ Serialización global. 
    - Modelos de consistencia relajados:
        - Son aqueyos que relajan el cumplimiento de las condiciones de la CS con el objetivo de incrementar las prestaciones.
- Sincronización 
    - Soporte Hardware y Software de sincronización.
        - ![](https://remnote-user-data.s3.amazonaws.com/PmjKn5IF6bANc9G2XvPmyBNQ1h-AVQZsUUBWVp1zVUdS02PpPTZyBaqc3hekN9YTnYkkgvEONM7D7lFvMDXbA6-NphhCAaJTi3xSLLgKivazKP2uu2H4E4EZL278nuZJ.png) 
    - Cerrojos:
        - Estructura software que permite la sincronizar varios flujos de instrucciones mediante dos operaciones:
            1. **Lock()** 
                - Un flujo de instrucciones ejecuta el lock() cuando quiere acceder a una SC (adquiere el cerrojo/lo ciera)
                - Requisitos a cumplir:
                    1. Si hay varios flujos que intentan la adquisición a la vez solo uno de ellos puede entrar
                    2. Todos los cerrojos que ejecuten lock() con el cerrojo cerrado tienen que esperar.
            2. **Unlock()**  
                - Todo flujo deve ejecutarlo al terminar de acceder a las variables compartidas para que el resto de las hebras puedan ejecutar su SC.
                - El objetivo es liverar solo uno de los flujos que estaban esperando.
                    - Requisito ⇒ Si no hay flujos en espera, permitirá que el siguiente flujo ejecute lock() sin esperar.
        - **Implementaciones:**
            - Cerrojo Simple: ↓ 
                - Implementación mas sencilla de todas, Toma de una variable compartida k que toma dos valores(1 ⇒ cerrado, 0⇒ abierto).
                - ```cpp
void lock(k){
	k=0;
}

void unlock(k){
	while(leer-asignar_1-escribit(k)==1){}
}
``` Funcion
                - 
