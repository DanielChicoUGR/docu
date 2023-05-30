- Introducción
    - Los Sistemas de Representación Estructurados tienen el objetivo de {{representar el conocimineto mediante grafos}}, ya sean conceptos o relaciones, además, facilitan la {{representación de este conocimiento humano}}.
    - Permiten {{por su propia estructura deducir hechos}}
    - Existen dos modelos clásicos de Sistemas de Representación Estructurados ↓ 
        - Redes Semánticas
        - Frames
- Redes Semánticas:
    - {{Precursor}} de los frames.
    - Pretende representar el lenguaje natural de forma simple y visual, como un grafo
    - Formalismo limitado, solo para dominios simples y forma de inferencia simple, no adecuado para tratar con formas de inferencia más sofisticadas. Inferencia basada en herencia.
    - Una red semántica se representa como un {{grafo dirigido etiquetado,}} donde se etiquetan los nodos y las conexiones.
        - Nodos→Representan conceptos, ya sea un objeto individual o una clase de objeto
        - Arcos→Representan relaciones binarias entre los conceptos.
    - Se debe tener cuidado con las deducciones ya que el sistema puede quedarse sin memoria por las deducciones que realiza.
    - Ejemplo:
        - ![](https://remnote-user-data.s3.amazonaws.com/-IjysUJjpXXRvS9KSelXWX2FRqyEQOUVBdzlZYPvGUKsD7CkiNSp01ELsE_UdxRJ81Rr7SlmrP-quhd6aDGyLQsXKijqXJ1vXpWZew7XOAOeFkwuPGumP2aVKaAcoT1y.png)![](https://remnote-user-data.s3.amazonaws.com/oYIXRnWW-uw2woMWrkE8_FQYF0w4O2ja_wcU_enoQwtUZqHS6mCZf_0_Vm5-RLZaqfczQSl8_bYrBQ0rzrPDL7ViJb_vdAmi9ApjIVYC1DUZC_DgxMJrrtL3aORdN1qU.png) ![](https://remnote-user-data.s3.amazonaws.com/JWxx05rJFjiKKuBomO_52qu9lEhO9ykWuznV8QZRKZKotB_yI6HiVSNKB4rSsaY3EyuLHxRbqnlM_bvlNn-rpC9p24eGsXaqFDR4I0_I7C0AsNvIAo6N7jC7UmgBLD-8.png) 
    - Relaciones Subclase-de e Instancia-de
        - Subclase-de e Instancia-de son dos relaciones que ise usan en todas las redes semánticas.
        - A través de ellas se realiza el proceso de herencia, que es la forma de inferencia asociada a las redes semánticas
        - En el lenguaje natural se corresponden con las expresiones "es un", "son"
        - ![](https://remnote-user-data.s3.amazonaws.com/KRzTohXSTnXp_nzVQIEbLe-5Km06CD6hdD02kN6UGumfENga9OkGOQpaz-LlN0ncvsA0dB6_ggbSvQhUKt5RxGL-9UHcxe3KkXDOauygm292Zf-c5TuE5dU2x9H2EOQz.png)![](https://remnote-user-data.s3.amazonaws.com/MyBzqMhCJPATN5WmSMkNDHX_MtquNcNPrFXHp3fKAXOnoyzeQgU0k9sKFGktSoQorxFrLPlbymBjy8sKbQgq378RKMqRoYScE6OMlsQ8dIHOrc9oblSvnTcRfl9sLFC9.png) 
    - Herencia
        - La herencia→es la forma de inferencia asociada a las Redes Semánticas.
        - Se corresponde con el razonamiento siguiente: {{"Las subclases y las instancias heredan las propiedades de las clases mas generales"}} 
        - Gráficamente se traduxcen en:
            - ![](https://remnote-user-data.s3.amazonaws.com/lOVQr96InhWrMtRwej3pJBIpCaLdOo5yQY_AkFYgzQBF0vpu7NrK3IzeFv7c2ODBzHvtrQxuqQO0v1xRfKgMJvPDr2DmhUnY6p6jPGuPp6jLH315HKfHHNSGV0ilFN9f.png) 
    - Excepciones a la Herencia
        - Puede ocurrir que una propiedad heredada no sea valida, posibles soluciones ↓ 
            - Hacer la propiedad sea por defecto; la propiedad no se hereda si el concepto ya contiene esa propiedad explícitamente en la red
            - Marcar esa propiedad como no heredable
        - ![](https://remnote-user-data.s3.amazonaws.com/Q3C0MjDO7GSB-7P6xX4TlpADBb8Scr3mhciSAqm701I62TOtGw5SfJeHxGrcHmXJ3Sf19x1pzOA0qBFi5xPoSQr2ijLPd_xKT3esIuftzcQfCNXrFw4r2F_jv7Kc9_nF.png) 
    - Herencia en Clips
        - Definición de conceptos y arcos:
            - (deffacts Conceptos
	(Concepto <etiqueta_concepto>)
	…
	(Concepto <etiqueta_concepto>)
)
(deffacts Arcos
	(Arco <etiqueta_arco> <etiqueta_concepto_origen> <etiqueta_concepto_destino>)
)
        - Herencia Semántica
            - (defrule Herencia_red_semantica
	(Arco Instancia_de|Subclase_de ?O ?C)
	(Arco ?Propiedad ?C ?V)
	=>
	(assert (Arco ?Propiedad ?O ?V))
	; Opcionalmente;
	(printout t “He deducido que por herencia de la clase “ ?C “, ” ?Propiedad “ de “ ?O “ es “ ?V” crlf)
)
- Redes Semánticas Extendidas
    - Introducidas para representar {{en una red semántica predicados que no sean binarios}} , de esta manera se puede representar {{clausulas de lógica mediante una red semántica}} 
    - Para establecer una equivalencia semántica entre la forma casual de la lógica y las redes semánticas, se pueden utilizar reglas de inferencia de lógica para manipular los nodos y arcos de la red
    - Representación de predicados unarios
        - ![](https://remnote-user-data.s3.amazonaws.com/_mdBV7T6Fy-hoFe4FZPNG8B32RZZozcBwnzz8IsJpIIa1bNIRjAGnWZ_n6U3lMBPBHB1uhVwZ_hSbn16b4BTKqLrBau8xThWlIvdLcHUIpKbbwLbLPlrhKXYAjScFzw4.png) 
    - Representación de predicado n-ario (n>2)
        - ![](https://remnote-user-data.s3.amazonaws.com/wr8iVhcnbG--UnlLAQ84qULV24XYNaDCp0Wm2yJ1f0pDIgOPq6AWexvTbOrEwFN6ov40FhlOoY67Q3KLbhRJegT7JvuNDjQglHBakYjSswszwYscGXDcUtAnYFtUJA3F.png) 
    - 
- 
