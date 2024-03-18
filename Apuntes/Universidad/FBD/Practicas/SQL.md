- Tipos de Datos
    - ![](https://remnote-user-data.s3.amazonaws.com/9S7i6YQDeDlp5k_xp0fgcWbRiQcLBs-56EBjZ7CO1tnhX4hSP9rtVeSKY__Rrr_sqG4XADTh6BrBORyY67_3qeGmMUqJFTcbIQhv0EmyP3rsjxb84OODb7k_xJCCCvRQ.png)  
    - Tipo de dato Fecha:
        - Sirve para almacenar datos relativos a fechas. Se almacena representando un valor del calendario juliano desde el 1/1/4712 AC al 13/12/9999 DC. Se almacena como un numero que representa el dia.
        - Oracle permite operaciones aritmeticas basicas con fechas.
        - El termino __**SYSDATE **__ devuelve la fecha y hora del sistema
        - Funciones especiales:
            1. **TO_DATE**
                - se genera un valor de tipo date a partir de la cadena suministrada como primer parametro con el formato de la cadena del segundo parametro
                - ```sql
TO_DATE('22/10/2005','dd/mm/yyyy')
``` 
            2. **TO_CHAR**
                - Permite recuperar un tipo de dato fecha con un formato concreto. Transforma el valor interno a una cadena de caracteres imprimible
                - ```sql
TO_CHAR(atrb_fecha,'dd-mm-yyyy')
``` 
            3. ![](https://remnote-user-data.s3.amazonaws.com/sD1BTrqy5ey3kl8KBzmHVwR6uWhijiRc_odzsIf3wxd1t2Hvyakcny7zjkJWr9ATH5NLiBnzVESNBUbfemu1qyk2dc3U0cLNK5VVJPri3ZKknM4It4whkQmRMx5HHNZx.png) 
- [DDL](../../../Cursados/FBD/Teoria/Tema 2 ⇒ Arquitectura de un SGBD (DBMS)/Lenguajes de una BD/DSL/DDL.md) 
    - Creación de tablas:
        - Sintaxis Básica:
            - ```sql
CREATE TABLE nombre-tabla(
nombre-atributo1 tipo-atributo1 [NOT NULL] [DEFAULT expr],
nombre-atributo2 tipo-atributo2 [NOT NULL] [DEFAULT expr],...
[PRIMARY KEY(nombre-atributo1, nombre-atributo2...),]
[UNIQUE (nombre-atributo1, nombre-atributo2...),]
[FOREIGN KEY(nombre-atributo1, nombre-atributo2...)
REFERENCES nombre-tabla(nombre-atributo, ...),]
[CHECK(condicion)]
);
``` Modificadores:
                - NOT NULL ⇒ evita que el atributo tome valores nulos
                - DEFAULT  __expr__  ⇒ hace que si no se introduce un valor para el atributo, por defecto toma el valor de  __expr__  
                - PRIMARY KEY ⇒ Establece el atributo como clave primaria de la tabla
                - UNIQUE ⇒ hace que no se puedan repetir valores de ese atributo entre tuplas (**Clave candidata**)
                - FOREIGN KEY ⇒ Establece el atributo como clave externa
                - REFERENCE  __nombre_Tabla(nombre_atributo)__   ⇒ Acompaña a FOREIGN KEY y estable a que atributo hace referencia la clave externa 
                - CHECK  __cond __ ⇒ indica que condicion tienen que cumplir los valores almacenados en ese atributo (Expresion exsplicita del dominio del atributo) 
        -  
    - Modificación del esquema de una table (poco recomendable):
        - ```sql
alter table  nombre_tabla add (atrb [tipo] ...);
``` 
        - Existen mas modificadores a parte del **add1** 
    - Eliminación de tablas:
        - ```sql
drop table nombre_tabla;
``` 
    - Descripción Tabla:
        - ```sql
describe nombre_tabla;
``` 
- [DML](../../../Cursados/FBD/Teoria/Tema 2 ⇒ Arquitectura de un SGBD (DBMS)/Lenguajes de una BD/DSL/DML.md)
    - Insercción de tuplas:
        - ```sql
insert into <nombre tabla> [col1,col2...]
	values (valor1,valor2...);
``` 
        - Version modificada para rellenar a partir de otra tabla de la base de datos.
        - ```sql
insert into <nombre tabla> [col1,col2...]
	(select colum1,colum2...
		from <nombre tabla 2>);
``` 
    - Consultar el contenido de una tabla 
        - Consulta de toda la tabla
        - ```sql
select * from <nombre tabla> 
```
        - Consulta de unos atributos concretos
        - ```sql
select atrb1,atrb2... from <nombre tabla>
```
        - Instruccion completa

```sql
	SELECT [ DISTINCT | ALL]
	expresion [alias_columna_expresion]
	{,expresion [alias_columna_expresion]}
	FROM [esquema.]tabla|vista [alias_tabla_vista]
	[WHERE <condicion>]
	[GROUP BY expresion {,expresion}]
	[HAVING <condicion>]
	[{UNION | UNION ALL | INTERSECT | MINUS} <SELECT instruccion>]
	[ORDER BY {expresion} [ASC | DESC]]
``` 

- Modificar Contenido de una tabla
        - ```sql
update nombre_tabla set  
--La parte del set se puede convertir en una consulta
	atrb1 ='nuevo_valor_1',
	atrb2 ='nuevo_valor_2' ,
	...
[where <condicion>]
``` 
    - Borrado de tuplas
        - ```sql
delete from <nombre tabla> 
-- Sin el where borra todas las tuplas de la tabla	
	[where condicion]
```
    - 
