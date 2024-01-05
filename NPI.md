### Localizaciones
#### Aula:

>Edifio B
>>Lado Izquierdo
>>> 0.1 ... 0.6
>>>1.1 ... 1.6
>>>2.1 ... 2.7
>>>3.1 ... 3.8
>>Lado Derecho
>>> 0.7 ... 0.8
>>> 1.7 ... 1.8
>>> 2.8 ... 2.9
>>> 3.9 ... 3.12
>Edificio A 
>> Aula -1.1 -> Planta -1
>> Aula Polivalente -> Planta -1
>Modulo A
>> A1,A2
> Modulo B
>>B1,B2
>>
#### Despacho
>Edifio A
>>Planta 1
>>>1...40
>>Planta 2
>>>1...40
>>Planta 3
>>>1...40
>>Planta 4
>>>1...40

#### Gestion

>Edifio A
>> Conserjería -> P.Baja
>> Secretaria -> P.Baja
>> Dirección -> P.Baja

#### Otro

> Delegación de Estudiantes
> Cafeteria
> Comedor
> Salón de Actos
> Sala de juntas
> Biblioteca
> Salas de estudio P1





### Base de datos
#### Entidades:
1. Profesor
2. Asignatura
3. Imparte (Rel m:m Profesor-Asignatura)
4. Clase (Rel 1:m Aulas-Imparte)
5. Nodos
6. NodosAdyacentes (Rel N:N Nodo:Nodo)
7. Sala
8. Aula
9. Despacho
10. Otro


#### Clases Relaciones ORM
1. despachoDe (Despacho -> Profesores (1:n))
2. TrabajaEn (Profesor -> Despacho (1:1))
3. ProfesorImparte (Profesores -> Asignaturas (n:n))
4. AsignaturaImpartida (Asignatura -> Profesor (n:n))
5. ClaseHora (agregation) (Imparte -> aula (1:1 teniendo en cuenta dia y hora, n:n sin tener en cuenta))
6. Adyacentes (Nodo -> Nodo)
7. OtherClassInfo,AulaClassInfo,DespachoClassInfo (Relación 1-1 de dependencia existencial entre las entidades de Aula y sus especializaciones) -> Faltaria añadir constraint de que una sala es siempre alguna de las 3.
8. 