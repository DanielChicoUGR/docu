- Paso a tablas:
    - Traducción de un conjunto de entidades fuertes.
        - Sea un conjunto E de entidades fuertes caracterizado por n atributos. Representamos a dicho conjunto por medio de una tabla llamada E, donde cada fila corresponde a una n-tupla que a su vez corresponde con un elemento del tipo E
        - Claves primarias:
            - La clave primaria de la tabla correspondiente está constituida por los atributos que forman la clave primaria en el conjunto de entidades.
    - Traduccion de un conjunto de entidades deviles.
        - Sea A un tipo de entidad débil con n atributos. Sea B el conjunto de entidades fuertes del que depende A con m atributos como calve primaria. Representamos a A como una tabla con una columna por atrivuto del conjunto siguiente: $${a1,a2,..an} U {b1,b2...,bm}$$ 
        - Claves Primarias 
            - La clave primaria de la tabla correspondiente está constituida por los atributos que forman la clave primaria en el conjunto de entidades del que depende, mas los atributos marcados como discriminadores o claves parciales.
    - Traducción de una relación.
        - Sea E una relación concreta que conecta los tipos de entidad E1,E2...,Em. Entonces, la tabla para R contiene n columnas donde n=n1+n2+..nm+nr, ni=numero de atributos de la clave primaria del conjunto de entidade Ei.
        - Segun la cardinalidad las calves: 
            1. Relaciones Muchos a muchos:
                - La clave primaria esta formada por la unión de todos los atributos que forman las claves primarias de los conjuntos de entidades que intervienen en la relación. En su caso puede que haya que añadir algunos atributos de la relación.
            2. Relaciones Muchos a uno:
                - La clave primaria esta formada por la unión de todos los atributos que forman las claves primarias de los conjuntos de entidades que intervienen en la relación con cardinalidad muchos
            3. Relaciones Uno a Uno:
                - En este caso tiene dos claves candidatas dormadas cada una de ellas por los atributos clave de cada conjunto de entidades que intervienen. HAy que elegit como clave primaria ina de ellas y la otra mantenerla como clave candidata.
            4. ![](https://remnote-user-data.s3.amazonaws.com/8e6oDYgBQCycDIcjr2dDq1sdfiZVlbt33Rfyyf-K_GAHRe8mcFkxdKonWMEWf654PLdi2F0vB-l79iTf2XKWfF5uoLRwKE5l1d9z9IgYag5Y-zV2QM8Vid64gLXH52Px.png) 
    - Tradución de relaciones de Herencia:
        - Se crea una tabla por cada conjunto de entidades que indica el diagrama.
        - El Conjunto de entidades más general pasa a ser una tabla según el criterio empleado para los conjuntos de entidades.
        - Cada uno de los conjuntos de entidades de nivel inferior dispone de una tabla propia. Constituida por todos los atributos propios del conjunto mas la clave primaria del conjunto de entidades superior (Actua como Clave principal, clave externa y clave candidata).
        - En el paso a tablas se pierde información relatica a las restricciones de clasificacion de la relacion de herencia
        - Claves principales
            - LA clave primaria de cialquiera de las tablas está constituida por los atributo que forman la clave primaria en el conjunto de entidades superior, este conjunto de atributos es, a su vez, clave externa a la clave primaria de la relación de nivel superior.
- 
- 
