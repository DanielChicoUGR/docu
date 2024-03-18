- Concepto de Base de Datos
    - Base de Datos ↓ 
        - Es un conjunto de **d****atos **relacionados almacenados sin redundancia para ser utiles a diferentes aplicaciones.
        - Operaciones sobre los datos:
            1. **Insertar **Datos
            2. **Obtener **datos ya existentes en la BD.
            3. **Modificar** datos existentes
            4. **Borrar** datos existentes. 
    - Sistema de Gestión de Bases de Datos ↓ 
        - Conjunto de elementos software con capacidad para definir,mantener y utilizar una base de datos.
        - Debe permitir:
            1. Definir estructuras de almacenamiento
            2. Acceder a los datos de forma eficiente y segura
            3. Organizar y actualización de los datos y el acceso multiusuario.
- Bases de Datos y Sistemas de Gestión de Bases de Datos 
    - Elementos involucrados en una BD:
        1. **Datos**
            - Dato operativo↔Pieza de información básica que necesita una organización para funcionar.
                - Pueden ser: ↓ 
                    - Ítem básico
                    - Atributo
                    - Relaciones
        2. **Hardware**
        3. **Software**
        4. **Usuarios** :
            1. Usuarios Finales→Aquellos destinados a usar la BD sin conocer nada de su implementacion interna.
            2. Programadores de aplicaciones→Aquellos que programan las apps que usara el usuario final. Interqactua con la BD a traves de su esquema logico.
            3. Administrador (BDA/BDM)→Administra el SGDB para que la BD cumpla con todos los requisitos que necesiten las apps y los usuarios.
- Concepto de independencia
    - Los datos se organizan independientemente de las aplicaciones que las vayan a usar o de los archivos que se guarden en ella.
    - Independencia Fisica
        - Definición→El diseño lógico de la BD, a todos los niveles, debe ser independiente del almacenamiento físico de los datos.
        - Ventajas:
            - Cambiar aspectos de la estructura física sin alterar el resto de elementos que componen la BD
            - Liberar a las apps de usuario de gestionar aspectos relativos al almacenamiento.
    - Independencia Lógica
        - Definición→Busca mantener la independencia de las dos estructuras lógicas que componen la BD 
        - Existen dos estructuras logicas:
            - Esquema logico general→Vision global de la BD
            - Vista de Usuario→Conjunto de datos a los que se le permite el acceso a un determinado usuario/app...
- Objetivo SGBD ↓ 
    - Garantizar la independencia de los datos
    - Tener un diseño y utilización centrada en el usuario.
    - El manejo de los datos de manera centralizada
    - No redundancia
    - Consistencia
    - Integridad
    - Fiabilidad
    - Seguridad
    - No redundancia→Los datos no deben estar duplicados y se gestiona el acceso a estos
    - Consistencia→Si una BD tiene varias copias del mismo elemento estas deben ser idénticas entre si
    - Integridad→Los datos almacenados han de corresponderse con la realidad que intentan representar.
    - Fiabilidad→Los datos deben estar protegidos contra fallos externos asi como tener mecanismos para recuperar información.
    - Ventajas
        - Usuario
            1. No hay que reescribir programas cada vez que se realiza un cambio en la BD
            2. El usuario final puede acceder a los datos
            3. Aparece la figura del Administrador de la BD
        - Sistema 
            1. Tener un control centralizado de la informacion de forma que aumente la seguridad, consistencia,fiabilidad...
            2. Tener criterios de uniformizacion
            3. Los mecanismos de acceso facilitan el acceso a los datos
            4. Equilibrio en requerimientos de conflictos
            5. Escalabilidad.
- 
- 
- 
- 
