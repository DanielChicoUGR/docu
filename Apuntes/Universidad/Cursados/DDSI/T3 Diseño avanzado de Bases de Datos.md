- El modelo Relacional:
    - Basado en el concepto de **Relación** que, formalmente, puede verse como un par de conjuntos (R,r) donde R es el esquema y r la instancia de la relación
    - El esquema es un conjunto de atributos con dominios asociados
        - $$R=\{A_1:D_1, A_2:D_2,\dots,A_n:D_n\}$$
    - La instancia es un subconjunto del producto cartesiano de los sominios que debe cumplir las restricciones semánticas y de integridad.
        - $$r \in D_1 \times D_2 \times \dotsi \times D_n$$
    - Visualmente, es una estructura bidimensional formada por columnas (atributos) y filas (tuplas)
    - Un conjunto CC (Clave Candidata) de atributos en una relación se dice que es una clave candidata si se verifica lo siguiente ↓ 
        - Unicidad→Para toda instancia de la relación, si dos tuplas de dicha instancia coinciden en los atrivutos de la clave candidata, entonces coinciden en el resto de atributos de la relación
        - Minimalidad→LA propiedad anterior no se verifica para ningún subconjunto propio de CC.
    - Un subconjunto de atributos SC en una relación se llama superclave si verifica la unicidad
    - Se llama clave primaria a una clave candidata elegida por el diseñador (solo una por relación)
    - **Reglas de integridad genéricas** ↓ 
        - Integridad de entidad→Los tributos de la CC no pueden tomar valores nulos
        - Integridad referencial→el valor de una CE debe ser igual a un valor de dominio activo de la clave primaria o nulo si la semántica lo permite. 
- Normalización:
    - Diseño lógico Relacional→proceso que permite generar un esquema relacional a partir de una representación conceptual (esquema entidad relación) de la información relacionada con un sistema dado. También se le conoce como paso a tablas.
    - El diseño lógico relacional obtenido a partir del esquema entidad-relación puede refinarse mediante un proceso de Normalización, propio del modelo relacional
    - **Objetivos de la Normalización** ↓ 
        - Corregir Defectos del modelo conceptual
        - Eliminar redundancias, problemas de actualización
        - Plasmar restricciones semánticas adicionales. 
    - Tratamos de conseguir un diseño relacional de una base de datos que cumpla una serie de caracteísticas, lo que garantiza su buen comportamiento
    - Las buenas propiedades que cumple una relación se denominan **formas normales.**
    - ![](https://remnote-user-data.s3.amazonaws.com/_nHmFDvl7yJJm42t2ipPISejyWx1VeofHGgZ_tPGwk1jqGtATuNjWvUiPfeEgKR4X9i_1GWcVGcycp7HwnrjKLWmutHpDUmLy3uSjDBpecJPi9eVqoGpUL4nLiO0nUfP.png)![](https://remnote-user-data.s3.amazonaws.com/xuihmuLMcvMf1_2uFKLlTDea6TfRMcUpArk395gxyw3c1yDldpioutAFjOAluG8nOAvI5mBf1Gv2C9uhdNf2-yDhBK8jOLWWg0b8jE3f_3tDyHe4WzDYPmTssMkgf_2h.png) 
    - Dependencia Funcional
        - Definición→Dada una relación R con n>0 atributos y dos subconjuntos de atributos de R llamados $\alpha$ y $\beta$, se dice que $\alpha$ determina funcionalmente a $\beta$ si para cualquier instancia válida de r de R y cualquier pareja de tuplas s y t de r que tengan iguales valoreds para los atributos del subconjunto $\alpha$, se verifica que tienen los mismos valores para los atributos del subconjunto $\beta$ 
            - De otra Manera:
                - La combinacion de valores de $\alpha$ determina la combinación de valores de $\beta$
        - Las dependencias funcionales establecen restricciones semánticas conocidas y que deben verificarse em los datos 
            - DNI ⇒ Nombre. Cargo⇒Salaraio
        - Una forma de conseguirlo es mediante un diseño adecuado de la base de datos, es decir, determinar los esquemas de tablas adecuados. Concretamente son aquellos que cumplen las formas normales 2FN, 3FN y FNBC
            - La 1FN (forma base de diseñar un modelo relacional):
                - **Pasos:**
                    1. Eliminar los grupos repetitivos de la tablas individuales
                    2. Crear una tabla separada por cada grupo de datos relacionados
                    3. Identificar cada grupo de datos relacionados con una clave primaria
                - **CheckList:**
                    1. Todos los atributos son atómicos. **Un atributo es atómico si los elementos del dominio son indivisibles, mínimos.** 
                    2. La tabla contiene una clave primaria única
                    3. La clave primaria no contiene atributos nulos
                    4. No debe existir variación en el número de columnas
                    5. Los campos no clave deben identificarse por la clave (dependencia funcional)
                    6. Debe existir una independencia del orden tanto de las filas como de las columnas, es decir, **si los datos cambian de orden no deben cambiar sus significados.**
                    7. Una tabla no puede tener múltiples valores en cada columna
                    8. Los datos son atómicos (a cada valor de X le pertenece un valor de Y y viceversa)
        - Un conjunto de dependencias funcionales en una tabla sirve asimismo para determinar TODAS las claves candidatas, como veremos mas adelante
        - Dependencia Funcional Completa:
            - Definicición→Dada una relación R con n atriburos y dos subconjuntos de atributos de R llamados $\alpha$ y $\beta$, se dice que $\alpha$ determina funcionalmente a $\beta$ **de forma completa **o **determina completamente a **$\beta$ si $\alpha$ determina funcionalmente a $\beta$ y no hay ningún subconjunto de atributos de $\alpha$ que determine funcionalmente a $\beta$ 
        - Dependencia Trivial:
            - Se llama a dependencia trivial a toda dependencia del tipo $\alpha \rightarrow \beta$ tal que $\beta \subseteq \alpha$
        - Atributo Primo
            - Definición→Cualquier atributo que forma parte de alguna clave candidata. 
        - 2FN (Segunda forma normal)
            - **Pasos:** ↓ 
                1. Tener la 1° forma normal
                2. Crear tablas separadas para aquellos grupos de datos que se aplican a varios registros
                3. Relacionar estas tablas mediante una clave externa
            - **Checklist** ↓ 
                - Está en primera forma normal
                - Todos sus atributos no primos dependen de forma completa de las claves candidatas.
            - Un buen diseño conceptual debería arrojar tablas que estan en segunda forma normal.
        - Teorema de HEATH
            - Teorema→Sea R una relación cin atributos A,B y C, donde se verifica $B \rightarrow C$. Entonces, la descomposición de R en dos relaciones: $R_1(A,B)$,  $R_2(B,C)$ es una descomposición sin perdidas.
            - **Preservación de dependencias:**
                1. Reflexiva
                    - $\forall \alpha,\beta \ |\ \beta \subseteq \alpha$ se verifica $\alpha \rightarrow \beta$ 
                2. Ampliación
                    - $\forall \alpha,\beta,\gamma \ |\ \alpha \rightarrow \beta$ se verifica $\alpha \gamma \rightarrow \beta \gamma$ 
                3. Transitiva 
                    - $\forall \alpha,\beta,\gamma \ |\ \alpha \rightarrow \beta  \land \beta \rightarrow \gamma$ verifica $\alpha \rightarrow \gamma$ 
                4. Union
                    - $\forall \alpha,\beta,\gamma \ |\ \alpha \rightarrow \beta \land \alpha \rightarrow \gamma$ verifica $\alpha \rightarrow \beta \gamma$ 
                5. Descomposición 
                    - $\forall \alpha,\beta,\gamma \ |\ \alpha \rightarrow \beta \gamma$ se verifica $\alpha \rightarrow \beta \land \alpha \rightarrow \gamma$ 
                6. PseudoTransitiva
                    - $\forall \alpha,\beta,\gamma , \delta \ | \ \alpha \rightarrow \beta \land \beta\gamma \rightarrow \delta$ verifica $\alpha \gamma \rightarrow \delta$ 
            - **Descomposición sin perdidas:**
                - Sea (R,r) una relación que se descompone en (R1,r1) y (R2,r2). se dice que la descomposicion es sin perdidas ⇔ 
                    - $$R_1$$ 
- 
- 
