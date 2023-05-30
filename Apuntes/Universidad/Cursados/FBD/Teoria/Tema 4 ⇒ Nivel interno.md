- Conceptos básicos
    - Una BD sirve para ⇒ almacenar de forma permanente grandes cantidades de datos
    - Con el proposito de ⇒ gestionar de forma efiicente los datos y su alamacenamiento.
    - [Nivel interno ](../../FBD/Teoria/Tema 2 ⇒ Arquitectura de un SGBD (DBMS)/Una arquitectura de 3 niveles/La percepción de los datos en un SGDB puede hacerse siguiendo 3 niveles de abstracción_/Nivel interno.md)  ↓ 
        - Expresa en última instancia, las operaciones sobre los datos (CRUD) en términos de actuacón sobre [paginas/bloques](../Teoria/Tema 4 ⇒ Nivel interno/Conceptos básicos/Pagina_Bloque.md) 
        - Provee al administrador mecanismos para optimizar el almacenamiento y el acceso a los datos
        - Se encuentra implementado en el SGBD
    - Pagina/Bloque→unidad minima de almacenamiento de la base de datos.
    - Nivel Físico ↓ 
        - Se encuentra implementado en el SO
        - Proporciona al sGBD una capa dde abstracción sobre el hradware
        - Realiza el acceso a los medios de almacenamiento mediante llamadas a los sercicios del sistem de archivos proporcionado por el SO.
    - 
- Dispositivos de almacenamiento
    - ![](https://remnote-user-data.s3.amazonaws.com/1Dekx_xXbUjppB8rawlSirCqsrNmnmfYt9uexqV3G34X9u2iKTaavU2CSsrkMvkE479UTFiovwq1kYYGUsgv2a9axjxjCpnKClkRUAW3yzUjMMUfYYciwGHhG_xuWmqX.png)
    - ![](https://remnote-user-data.s3.amazonaws.com/l9fkrwAeyURFlERvqEviqx5x_F4C_z-eFhbEPeKHHtZC6KOv2Lub6pMvVmRDD4ZJf8FJaVxDEiMglkfgHseneyHHeyROkkaH3DWxDnUo6YXIVQL3rreh7VWI-uqNtBWk.png) 
    - 
- Métodos de acceso a la BD almacenada
    - ![](https://remnote-user-data.s3.amazonaws.com/quUxoMf17IzFSyuX6dQ8HLCsVOTrIVLRp-6o_Cf9R6HWfn2QCBMqbxayLPCd0r894KRbySOEkzxI73PTEBU6mrsrFnU8QFuXl2uv91c3nTgobnWWBTxscJoPSSl9Zgbf.png)Se crea un archivo en el disco con el que se gestionará la información de dicha tabla, se crearan tantos bloques como se vayan necesitando
Cada vez que se hace una petición de acceso a un dato, se devuelve el archivo almacenado
    - Proceso de almacenar registro en una representación física. 
    - ![](https://remnote-user-data.s3.amazonaws.com/n8s4wjjjB6uZ3UG1VEwTV7l2ErwoR-RxExOdxZZ4QKfOBMSfkdvqJHfJRVISWBlqg1GMB1Otr7x6GPEzKQ9Z2QX1XOSR3JiYpTN00DzQBr2QgghUx64oAxKCETQT86aK.png) 
    - Para quue el Gestor de almacenamiento pueda localizar un registro almacenado, se utiliza el RID (Recod Identifier) ⇒![](https://remnote-user-data.s3.amazonaws.com/cQ1dm1xmz-yHRP8xft078Sm5Y-gYKW9NYNYfge07oNVsGyvtsxrRI8Jl5KZv39b8RudcdF_IrHnZoBrcMqejAkiGcCS-SIVgmdbD2zX1dzP6t-GAD-TucwyMHBqvrhDF.png) 
    - Registro:
        - Se compoe de ↓ 
            - Cabecera ⇒ Número y tipo de columnas que lo integran
            - Datos ⇒ Contenidos de las columnas
        - Las páginas o bloques de la BD deben tener un tamaño múltiplo de las páginas del SO (Unidad minima de E/S)
        - Para recuperar un registro almacenado hay que determinar la página de BD que lo contiene y entonces recuperar los bloques de disco que la integran.
        - Hay que organizar la estructura de almacenamiento y los métodos de acceso.
            - De forma que se optimice la interacción con los dispositivos de almacenamiento. 
        - **Se debe minimizar las operaciones de E/S al almacenamiento secundario.**
    - El gestor de discos:
        - Es el medio de comunicación entre el SGBD y la BD almacenada en los discos del SO
        - El gestor de discos organiza los datos en conjuntos de bloques o archivos del SO
        - Funciones ↓ 
            - Crear un nuevo archivo
            - Eliminar un archivo de sistema SO
            - Añadir un bloque nuevo al conjunto de bloques c
            - Eliminar el bloque b del conjunto de bloques c
            - Devolver el bloque b del conjunto de bloques c
            - reemplazar el bloque b dentro del conjunto de bloques c
    - Gestor de archivos del SGBD
        - Componente del SGBD que se encarga de  ↓ 
            1. Hacer la trtansformacion entre {Campos,registros,archivos almacenados} a Bloques y conjustos de bloques que pueda entender el gestor de discos
            2. Organizar los datos de manera que se minimice el tiempo de recuperación de datos.
        - Funciones específicas ↓ 
            1. Crear un nuevo archivo almacenado y asociarlo con un conjunto de páginas o bloques de la BD
            2. Eliminar un archivo
            3. No recuperar el registro almacenado  __r__  del archivo almacenado  __a__  
                - Normalmente, el SGBD proporciona el RID
                - Solo hay que oobtener en memoria la página que contiene el registro para extraerlo
            4. Añadir un nuevo registro almacenado al archivo almacenado  __a__ . Hay que localizar la página de BD más apropiada de las pertenecientes al archivo almacenado. 
                - Si no se pudiera, se solicita una nueva página
                - Se devuelve al SGBD el RID nuevo
            5. Eliminar el registro  __r__  del archivo almacenado  __a__  
                - Hay que recuperar la página de BD que contiene dicho registro y marcar el espacio ocupado por el registro en dicha página como disponible.
            6. Actualizar el registro  __r__  en el archivo almacenado  __a__ 
                - Recupera la página de la BD que contiene el registro que se desea actualizar.
                - Trata de sustituir la información. Si no puede, se intenta ubicar en otra página
1. Representación de la BD en el nivel interno
    - La BD se representa de difarentes formas en los diferentes niveles de la arquitectura del SGBD
        - Su representacion en el nivel interno no tiene porqué coincidir con su representación a nivel conceptual.
        - Cada donjunto de registros del mismo tipo no tiene por qué ser un mismo archivo.
        - 
    - El nivel interno debe traducir als estructuras del nivel conceptual a otras estructuras intermedias más cercanas al almacenamiento real de los datos.
    - Agrupamiento:
        - La bd en el nivel interno→Conjunto de páginas en las que se vvan ubicando los registros
        - Agrupamiento intra-Archivo↔Ubicar en una página registros del mismo tipo
        - Agrupamiento Inter-Archivo↔Ubicar en una página registros de distinto tipo.
2. Organización y métodos de acceso
    - Objetivo ⇒ Minimizar el numero de accesos a disco ⇒ minimizar la cantidad de páginas de BD involucradas en una operación de BD
    - Criterios para medir la calidad ↓ 
        - Tiempo de acceso a los datos requeridos
        - Porcentaje de memoria ocupada por los datos requeridos con respecto a las páginas de BD que los contienen.
    - Niveles de trabajo:
        - Organización de registros de datos a nivel de almacenamiento.
        - Adicción de estructuras complementarias para acelerar el acceso a dichos registros.
3. Organización secuencial
    - Fichero de acceso secuencial ↓ 
        - Aquel donde los registros están almacenados consecutivamente
        - Para acceder a un registro determinado debemos pasar obligatoriamente por los registros que le preceden
        - Los registros suelen estar ordenados por una clave (normalmente fisica ⇒ Dir Mem)
    - ![](https://remnote-user-data.s3.amazonaws.com/nIKc4YK4ZkYI8C3_WETuy1doZvMn7T8m7j7UJDjeQt6-MwlBExUvNitqHKmyNtqCS-MGgpVTJTG-Oj4cBWDddFZ4dEHEv05O96OhsrmDeRh_WrM7mtxPM0U6fB9B8hu5.png) EJEMPLOS:
        - Mostrar laq relación completa de departamentos
        - 
    - Operaciones sobre Archivos secuenciales:
        1. Inserccion:
            - Busca el blioque que le corresponde:
                - OP1⇒ Si hay sitio, se inserta el nuevo registro
                - OP2⇒ O se crea un nuevo bloque o se crea un bloque de desbordamiento.
        2. Borrado:
            - Busxcar el registro
            - Puede implicar una reorganmización local de los registros de un bloque
    - Este tipo de archivos genera una se4rie de inconvenientes a la hora de acceder a rangos de datos ...
    - Se subsana haciendo uso de estructuras adicionales sobre estos archivos secuenciales que aceleran la localización de los datos y disminuyen el numero de bloques en disco. 
4. Indexación
    - Objetivo→Disminuir el tiempo de aceso a los datos por una clave de búsqueda, Similar a la idea de un índice en un libro.
    - Ficheros indexados
        - ![](https://remnote-user-data.s3.amazonaws.com/jnXGWy_lFfsc-djLNEedMcLh04iZn_NMTFU_thE_J8c7L1DPSEIdDlYunR8kxLDtGikOzHO-XHnrWrEZCSbh3VcjrO5slWB5RYhYChLDhtIQGIfWWwix1DnFzPcX_M_Z.png) 
        - Partimos de un fichero secuencial sobre el que disponemos una estructura adicional: fichero indice.
        - Registros:
            - Campo clave ⇒ la clave de búsqueda
            - Campo de refferencia ⇒ Contiene el RID del registro
        - Son mas pequeños que los ficheros de datos pero hay un fichero indexado por cada archivo secuancial de almacenamiento.
        - Tipos:
            - Índice Primario↔La clave de búsqueda es el mismo campo clave por el que está ordenado el fichero secuencial de datos.
            - Índice Secundario↔Construidos sobre otros campos que no sean la clave física del fichero de datos.
        - Proceso de consulta:
            - Se consulta sobre el valor de una clave.
                - Sobre el índice localizamos la clave (recorrido secuencial)
                - Obtenemos el RID del registro requerido
                - Vamos a disco para recuperar el bloque de datos donde se encuentra el registro señalado.
            - Se consulta sobre un rango de valores.
                - Búsqueda en el índice por valor de la clave de la cota inferior
                - Recorrido de las entradas del índice que están en el iintervalo, recuperando los registros correspondientes gracias a su RID
        - Proceso de Insercción:
            - Las mismas operaciones que en el fichero secuencial
            - Hay que actualizar también el índice
        - Proceso de borrado:
            - Borrado de un registro en el fichero de datos
            - Borrado de una entrada en el índice
        - Se pueden generar índices sobre mas de un campo
- Índices no densos
    - Registros :
        - Componentes ↓ 
            - La clave de búsqueda
            - La dirección de comienzo del bloque donde puede encontrarse el registro deseado
        - El número de registros se reduce al número de bloques del fichero de datos.
            - El acceso secuencial al indice no denso se acelera
    - ![](https://remnote-user-data.s3.amazonaws.com/An8o6-s2nfU8jggq4K65aTKOVHejjKZypcR4QqTphrFwzXOsl2eoMeBsUQ3H3QKqERXzAZoWFhQ32tbVL6s2H2NkiNUqOcj_D5_-lkwn947CA_MXxPl_hyIuMLIOGTzF.png) 
    - Diferencias en el proceso de búsqueda:
        - Una vez encontrado el bloque donde **PODRÍA **encontrarse el registro:
            - Se carga el bloque en memoria
            - Se busca el registro en el bloque
        - No se tiene garantía de encontrar el registro hasta consultar por completo el bloque de datos leido.
    - Los indices no densos solo se pueden generar sobre la clave física.
    - Su mantenimineto es menos costoso debido a que solo se han de actualizar cuando la operaci on afecta al valor representativo del bloque.
- Índice jerárquicos
    - La idea es crear índices sobre índices.
    - Un índice multinivel esta formado por ↓ 
        - Un índice de primer nivel sobre el fichero de datos.
            - puede ser denso o no denso
        - Otros indices no densos , construidos sucesivamente unos sobre otros
    - El tamaño de los bloques se establece con la idea de optimizar cada una de las operaciones de acceso al disco físico.
    - Se reduce el número de accesos a disco para localizar un registro.
        - En el peor de los casos tantos como niveles`
    - Se dificulta su mantenimiento
    - ![](https://remnote-user-data.s3.amazonaws.com/FP3F2pE7KAiBbOdAh51wATzyQW7QH4Uzyw4cPZl4CBppOeAn2E_nBPbDTCUGTQrU--5IOa36AUKbf2djVApWSh1NFmpV0QJlikXnpW7f91JVY7_PDCxyglzwmnLV9iNv.png) 
- Árboles B+
    - Generalización de los arboles binarios bien balanceados en la que los nodos pueden tener más de dos hijos.
    - Todos los valores de la clave se encuentran almacenados en los nodos hoja
    - Estructura árbol B+ ↓ 
        - Nodo nivel superior ⇒ Raiz del árbol
        - Nodo de nivel inferior ⇒ hojas
        - Cada nodo que no sea hoja tiene como máximo M hijos
        - Cada nodo que no sea hoja o raíz tiene como mínimi (M+1)/2 hijos
        - Todos los nodos hoja aparecen al mismo nivel
        - La raíz tiene al menos dos hijos si no es un nodo hoja
        - LAs claves contenidas en cada nodo nos guiarán hasta el siguiente nodo del nivel inmediatamente inferior
        - Un nodo no hoja con n hijos contiene:
            - n-1 valores de clave almacenados
            - n punteros $P_i$ que apuntan a un nodo hijo 
    - Restrucciones de los nodos ↓ 
        - Los valores de clave $C_i$ están ordenados dentro del nodo
        - Los valores x del subárbol apuntado por $P_i$ cumplen:
            - $C_{i-1} \leq x < C_i$
            - Excepto para:
                - $i=1 \rightarrow x<C_1$
                - $i=m, \rightarrow x\leq C_m$ 
        - ![](https://remnote-user-data.s3.amazonaws.com/yQ2FCJTc6W_V53pyMoRB4d4sLIPnBlqafmdVCNL0zrDmJ1us9TyQvguvDx3iYv_ZzXBWLUFrURGpDMY5EBDkzb3JNRgLveyUJf0yWAeeRWOwjR8A4A3YWEg82olVtZ0k.png) 
    - Nodos Hoja
        - Estructura ↓ 
            - Pareja clave-RID
            - Punteros al siguiente nodo hoja
            - Algunas variantes también tienen punteros al nodo hoja anterior
        - La lista concatenada de nodos hoja (conjunto secuancia) es util a la hora de consultar por intervalos de valores
        - ![](https://remnote-user-data.s3.amazonaws.com/JZ2gitlcdIXiRo5zyE_TUQ7QBc2xlpxadgz3LmtqXl1lDDKERpIeTWevF6Aid6gj4aY0bc9oJtr0raYSl7moF9LQ-_2KXA2onmITc0xUK2-3GHcFLRXtMEHed3lPmQGf.png)
        - Restricciones ↓ 
            - LAs claves aparecen ordenadas en cada nodo
            - Todas las claves han de ser menores que las del siguiente nodo en el conjunto secuencia
            - Los nodos han de estar como mínimo rellenos hasta la mitad
            - Todos los nodos hoja se encuentran en el mismo nivel
                - El árbol esta equilibrado
                - Todos los caminos del nodo raiz un nodo hoja tienen la misma longitud
    - Proceso de consulta
        - Localización de un registro:
            - NAvegamos desde la raíz bajando niveles
            - Buscamos el registro en el nodo hoja y, en su caso, recuperamos el registro del fichero de datos gracias al RID
        - Consultas por rango:
            - Se localiza el nodo hoja que contiene el valor inferior
            - Se recorren los nodos hoja hasta alcanzar el superior, recuperando los registros pertinentes del fichero de datos.
    - Proceso de insercción y borrado
        - Se utilizan algoritmos que garantizan que el árbol resultante sea equilibrado
- Árboles B
    - Modificación de los árboles B+ en el cual no todos los valores de la clave se almacenan en los nodos hoja, hay algunas claves que se almacenan en nodos internos conforma se crea el árbol
- Uso de Árboles B+ en BD
    - ![](https://remnote-user-data.s3.amazonaws.com/VtzNjRQySMGGwNS2dmCLB7GLOgmER0vCQ9fcs0tBSDgud2-31MBuC8l-QeH_rFcs9huT5XOz2QoKbFbbu_4GHTRMQj_UmCqRHPmicpH594-35CpeKfmLhLgxH7zaB6xr.png)  
    - Tablas organizadas por Índices (IOT)
        - Tablas Organizadas por índices→Estructura comparada con la de los índices que devuleve la tupla a consultar en vez de su RID
        - ![](https://remnote-user-data.s3.amazonaws.com/vbF08sPl2Gw6FrJyMd2YleZPM903hyhEnRe44VeHWyNXPrQyNAm4FqpvIqoBpkukcRncZru0yGXHpf6Gz4QA2fGDRTeoXmHzlvdsV-jh5c3Zj8nFHy13A8Hgopty3lhH.png)  ![](https://remnote-user-data.s3.amazonaws.com/ky82AUsODTnf0_Y4ffQMyRil3-C40aR_wJAGntCOicUxkRvhtLD5-DCYToIMHCbhyFtA2bhVOYew6xeOXMX8x3S5fUYUOIpH_5bSzdZngOJdCR7dSqkE5sDvWBtGBGo4.png) 
        - Comparativa entre Tablas y IOT 
            - ![](https://remnote-user-data.s3.amazonaws.com/usj7XWHPdhurIdQKnTNegkhJCxo-hU3FBFSOYPrLf5OmUv3_ORp1aSSXdE5I8HvkORHI2MW8GOtcs52_RKDqHt8BDBJIhlysLw6ODdziL8t-CBj_47j9j03PcBOq-cD5.png) 
    - Indice por clave invertida (reverse index)
        - Invierte los datos del valor de la clave. Este indice es adecuado apra búsquedas basadas en predicados =.
        - ![](https://remnote-user-data.s3.amazonaws.com/IF8g2tfvKvD3WUSaibhVVADVhKmhdyi1sgW3nBDC7N4LTMYHfJEmznQfZKq8FrnLVio6efu5I-opqTzcfL0FSWvL8HjZ0NqZbkFZM-X3pBrhlT0b1hFqAtsLMqg5d3lc.png) 
- Índices BITMAP
    - Definición→Para cada valor que toma la clave almacena una secuencia de bits (tantos como tuplas contenga la tabla), el bit 1 indica que ese valor está presente en la tupla, el 0 que no lo está
    - ![](https://remnote-user-data.s3.amazonaws.com/Pn3xz1UPR7eS2NxtCip3EMsoZ7CZQjybKzAflrqJu4im4DLwuVyxY0tYwFNkmLlHfGFn0xwp57oMPsIti7JPeh6zZViXp7bES_USRKPwH2LZrkc_OzJLd8WWcf0fzg4o.png) 
    - Comparativa entre BITMAP e indices basados en B-tree
        - ![](https://remnote-user-data.s3.amazonaws.com/6Tywq7kzMGnO80ddhbI5_db0gs4w_fx2V4rGTAoKw6NJkuwiXbRtiUAsYCbPWy1ZPwjFEcwe-Gs0bX8HYqOhKd825SQ68lPvI_uCpMCPwTafcLUowoBVXGeV3yEjnt6g.png) 
- Acceso directo
    - Que hace?→Calcula directamente la dirección de un registro mediante la aplicación de un algoritmo o función sobre un campo determinado del mismo.
        - El campo debe identificar univocamente el registro
    - No necesita una estructura de datos adicional.
    - Funcionamiento:
        - Normalmente no es posible estableces una clave física que sea totalmente correlativa y única para cada registro
        - Hay que buscar un algoritmo que transforme los valores de un cierto campo en una dirección.
            - Entrada ⇒ Campo clave
            - Salida ⇒ valor entero positivo fácilmente transformable en RID
        - ![](https://remnote-user-data.s3.amazonaws.com/kZ1C1Ssiysv3M7hrtTzjmkzt9Y0zvuqOIF8Bv8eKF5I5nIVQ82AQ0FKQfH0QFmr4yTzCG9uNW8A8d6iygqjiWefVDmUmqvV_ZfZ-0mS6162nxVBpBBYo1-OgGIeXDHaN.png) 
        - 
    - Los algoritmos de direccionamiento no suelen mantener el orden de las claves. Esto genera:
        - Los registros no están almacenados según el orden de su clave física.
        - Problemas con la recuperación por intervalos.
    - Ejemplos de algoritmos de Hashing:
        - Clave alfanumerica:
            - Primero se transforma en un valor numérico y se obtiene su dirección de ahi
        - Clave numérica:
            1. Cuadrados centrales:
                - Se eleva la clave al cuadrado y se eligen tantos números como sea necesario 
            2. Congruencias:
                - Se divide la clave por M y se toma su resto
            3. Desplazamiento:
                - Se superponen adecuadamente los dígitos de la clave y luego se suman
            4. Conversión de base:
                - Se cámbia de base de numeración y se suprimen algunos dígitos resultantes.
    - Problemas:
        - Los algoritmos producen huecos.
            - Huecos→Zonas vacías del rango de salidda, no asignadas por el algoritmo. Se traducen en memoria sin utilizar en el disco.
        - Gestión de colisiones y huecos:
            - Combinar el acceso directo con una gestión mediante listas de colisión:
                - Zona de desbordamiento
                - Colisión:
                    - El registro problemático se almacena en la zona de desvordamiento
                    - Los sinónimos se conectan mediante una lista.
                        - Sinónimo→Registros con claves que producen colisión.
        - Otras problematicas:
            - Las listas de sinónuimos crecen mucho
        - Salvo que el campo clave se diseñe para ello, es prácticamente imposible encontrar una transformación que dé un valor entero positivo en un rango de valores limitado tal que no haya dos valores distinto de clave que generen la misma dirección (Colisión)
            - 
- Hashing básico
    - Principal problema del acceso directo ⇒ los valores de las claves no están uniformemente distribuidos en el intervalo [0,m].
        - Se acumulan en una parte del intervalo
        - Solución ⇒ Asignar más espacio a esa parte del intervalo.
    - Operativa:
        1. Se divide le espacio del ficher en cubos ("Buckets")
        2. El algoritmo de direccionamiento asigna cubos, no direcciones concretas
        3. En cada "cubo" puede haber más de un registro.
        4. Ciertos rangos de valores tienen asignados más cubos que otros.
        5. Se complementa con el uso de "Cubos de desbordamiento"
    - Parametros:
        - Número de cubos
        - Tamaño de los cubos (Relación con bloques físicos del disco)
        - La transformada clave/dirección, que debe tener en cuenta la distribución de la clave segúín rangos para que unos cubos no se llenen mucho y otros se queden muy vacíos.
    - Insercción de un registro ↓ 
        1. Transformar la clave
        2. Localizar el cubo correspondiente
        3. Si hay sitio se inserta el registro en un cubo de desbordamiento conectandolo con el cubo que realmente le corresponde mediante punteros
    - Busqueda de registro ↓ 
        1. Transformar clave
        2. Localizar cubo correspondiente
        3. Realizar busqueda secuencial dentro del cubo
            - Si hemoss encontrado el registro el proceso termina
            - Si no se encuentra, se impone un "Barrido por punteros" a través de los cubos de desbordamiento.
    - ![](https://remnote-user-data.s3.amazonaws.com/5c-t7sYO3VO3lZxoWKrqf4dywnKoBun8-ZSn8zKxbnYp27z4zersOZbFmperfMqN7yc0UZOcD5QLe3Y1U4KrSV0lFYBKuKvQ8PAuyASD6sT7HCeR1TPNjbGq9p29uKjx.png) 
- Hashing Dinámico
    - Problemas del hasing básico:
        - Necesario conocer la distribución previa de las claves para asignar adecuadamente los cubos.
            - En otro caso siguen apareciend huecos/colisiones
            - Al aumentar el número de registros, aumentan los registros en páginas de desbordamiento.
            - Se hacen necesarias las reorganizaciones.
    - Hashing dinámico ↓ 
        - Trabajar de forma dinámica
        - Se parte de una configuración uniforma de pocos cubos
        - Los restantes se van generando bajo demanda
            - Se asignan a los rangos conforme la afluencia de registros los demanda
    - Técnica:
        - El valor transformado del campo clave nos lleva a la entrada de una tabla índice que se almacena en memoria
        - Allí está la dirección del cubo donde se encuentran los registros que tienen asociado este valor transformado
        - Puede ocurrir que varias entradas de la tabla conduzcan al musmo cubo
        - Proceso ↓ 
            1. Inicialmente, todas las entradas apuntan al mismo cubo
            2. A medida que vamos insertando registros, se van generando nuevos cubos y cambiando las salidas de la tabla índice.
    - Algoritmo:
        - Datos iniciales:
            1. k⇒Clave física para direccionar
            2. k' =h(k) ⇒ valor entero entre 0 y M
            3. n ⇒ número de bits que tiene k' en binario
            4. $d\leq n$ ⇒ los d primeros dígitos de k' seleccionan en el cubo donde está el registro y se llama psudollave
            5. $b<d\leq n$ ⇒ inicialmente el archivo tienen $2^b$ cubos distintos, como máximo tendrá $2^b$ 
        1. Se considera una tabla índice en memoria con $2^d$ filas
        2. En la primera columna de esta tabla se sitúán todas las posibles sucesiones de d dígitos binarios
            - d⇒ profundida global de la tabla
        3. En principio todas las entradas cuyos b primeros dígitos son iguales apuntan al mismo cubo.
            - Alli se almacenan los registros cuyo valor de k' tiene esos b primero dígitos
        4. Todos los cubos tienen en principio "profundidad local" igual a b
        5. Cuando se llena un cubo se divide en 2, poniendo en uno de ellos los registros con el dígito b+1 de k' a 0 y en el otro los que lo tienen igual a 1. La profundidad local de estos cubos aumenta una unidad.
- Uso del Hash en SGDB 
- 
