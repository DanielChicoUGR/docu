Aplica distintos puntos de vista según las partes interesadas en un sistema software. Los objetivos de este estándar son
1. Asumir una **interpretación amplia del concepto de arquitectura** en sistemas software intensivos
2. Establecer un **marco de trabajo conceptual y un vocabulario** para hablar de los aspectos arquitectónicos del sistema
3. Identificar y declarar **practicas** arquitectónicas solidas
4. Permitir la **evolución de estas prácticas** conforme evolucionan tecnologías que sean relevantes. El marco debe ser suficientemente general para acoger las técnicas actuales y suficientemente flexible para que pueda evolucionar
## Entidades conceptuales consideradas
![[Pasted image 20240617191146.png]]
### [[Descripción arquitectónica]]
### Stakeholder
Parte interesada. Cualquier individuo, clase o componente externo, institución o rol interesado en el sistema y/o en su realización
Los grupos mas importantes de partes interesadas son:
- Los mas afectados por las decisiones arquitectónicas, como **usuarios**, operadores o los clientes que pagan por la realización del sistema
- Los que influyen en la forma y en el éxito de desarrollo, como los **clientes**
- Los que deben incluirse por razones organizativas o políticas, tales como los **administrativos**, un equipo encargado de la gestión de la arquitectura global o alguna persona con autoridad en la empresa
### Concern
Cualquier area de inquietud de la arquitectura que tengan las partes interesadas en el sistema
### Vista
Cada una de las partes en las que se divide una [[Descripción arquitectónica]]
El estándar no exige unas vistas concretas pues estas dependen de la técnica usada, sino que lo deja **a criterio de los usuarios** del estándar
### Punto de vista
Contiene las **reglas** por las que se rigen las vistas concretas
