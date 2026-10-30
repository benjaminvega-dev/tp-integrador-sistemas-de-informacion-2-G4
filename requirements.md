

# Requerimientos

Completar a partir de los fragmentos de relevamiento del caso. Seguir
la convención de `skill/SKILL.md` (atómico, verificable, sin tecnología
mezclada).

Frente 2 · Emisión de pólizas de automotor · Grupo G04. Convención de `skill/SKILL.md`: atómico, verificable, sin tecnología mezclada. Misma tabla que la 2.2 del informe (se agregaron las columnas de issue, nivel y tipo, y criterio).

## Requerimientos funcionales

| ID | Requerimiento | Fragmento(s) de origen |
|----|---------------|--------------------------|
| RF-01 | G04-2 | El sistema debe registrar una solicitud de emisión de póliza de automotor para un cliente y un vehículo ya registrados, con el año del vehículo, el valor asegurado, los datos del riesgo (cobertura RC, TC o TR; edad del conductor; zona de radicación; siniestros de los últimos 24 meses; guarda en garaje) y las condiciones comerciales (débito automático, otra póliza vigente, antigüedad del cliente), y dejarla Solicitada. [NEEDS CLARIFICATION: los valores posibles de la zona de radicación no figuran en el caso ni en el acta. Decide R. Ferreyra.] | Usuario / Funcional | SIGA 6.1.3 «Emisión de pólizas»; Caso §2.1 (alta de cliente y de vehículo), §3.2 (paso 3) y §6 (coberturas); hallazgo E2-1 | Con los datos completos la solicitud queda Solicitada; si falta alguno, no se registra. |
| RF-02 | G04-5 | El sistema debe rechazar automáticamente toda solicitud de un vehículo de más de veinte años de antigüedad, sin excepciones ni posibilidad de forzar la carga. [NEEDS CLARIFICATION: ni el caso ni el acta dicen cómo se calcula la antigüedad (¿año en curso menos año de fabricación?) ni en qué estado queda la solicitud rechazada. Decide M. Duarte.] | Negocio / Funcional | Acta 3.3 (decisión de M. Duarte); Caso §4 (M. Duarte y S. Roldán) | Con un vehículo de 21 años se rechaza y no se puede forzar; con uno de 20 años sigue. |
| RF-03 | G04-6 | Cuando el valor del vehículo supera un umbral, el sistema no debe emitir la solicitud en el acto: debe pasarla a Suscripción; por debajo del umbral debe emitirla en el acto. [NEEDS CLARIFICATION: el importe del umbral no está fijado (Acta 4.2) y la fecha comprometida (12/09/2026) ya pasó. Decide R. Ferreyra.] | Negocio / Funcional | Acta 3.4 y 4.2; Caso §3.2 (paso 5) y §4 (J. Ponce) | Pendiente: no se puede definir hasta que se fije el umbral. |
| RF-04 | G04-7 | El sistema debe permitir que Suscripción pida una inspección previa por parte de un perito sobre una solicitud En revisión técnica, y mantenerla En revisión técnica hasta que haya dictamen. | Negocio / Funcional | Acta 3.4 (A. Pampín, con conformidad de la Gerencia Técnica); Caso §1.1 (Suscriptor, Perito) y §3.2 (paso 5) | Con una solicitud En revisión técnica, al pedir la inspección previa sigue En revisión técnica y queda registrado el pedido. |
| RF-05 | G04-8 | Cuando Suscripción registra un dictamen favorable sobre una solicitud En revisión técnica, el sistema debe dejarla Validada. | Negocio / Funcional | Caso §1.1 (Suscriptor) y §3.2 (paso 6) | Con dictamen favorable la solicitud pasa de En revisión técnica a Validada. |
| RF-06 | G04-9 | Cuando Suscripción rechaza el riesgo de una solicitud En revisión técnica, el sistema debe dejarla Rechazada y no permitir emitirla. [NEEDS CLARIFICATION: el caso no dice qué datos registra el rechazo, si puede reabrirse ni qué significa «aceptar con condiciones». Decide R. Ferreyra.] | Negocio / Funcional | Caso §1.1 (Suscriptor) y §6 (Suscripción, Rechazo) | Con el rechazo la solicitud queda Rechazada y no se puede emitir. |
| RF-07 | G04-10 | El sistema debe calcular el premio de la solicitud y mostrarlo antes de emitir. [NEEDS CLARIFICATION: la fórmula depende de los descuentos: J. Ponce dice que se suman y H. Vidal que están topeados (Acta 4.3); el cliente VIP lo define M. Duarte por antigüedad y R. Ferreyra por cantidad de pólizas (Acta 4.1). Deciden M. Duarte y H. Vidal (4.3); M. Duarte y R. Ferreyra (4.1).] | Negocio / Funcional | Caso §3.2 (paso 4) y §4; Acta 3.4, 4.1 y 4.3 | Pendiente: no se puede definir hasta que se decida la fórmula. |
| RF-08 | G04-11 | Al emitir una solicitud Validada, el sistema debe asignarle un número de póliza único y dejarla Emitida. | Sistema / Funcional | Caso §2.1 (Emisión de póliza) y §3.2 (paso 6) | Dos emisiones seguidas reciben números distintos y quedan Emitidas. |
| RF-09 | G04-12 | El sistema debe entregar al productor los datos de la póliza emitida: número, cliente, vehículo, cobertura y valor asegurado. | Sistema / Funcional | Caso §3.2 (paso 6) y §5 (Póliza) | Tras emitir se ven el número, el cliente, el vehículo, la cobertura y el valor asegurado. |
| RF-10 | G04-13 | El sistema debe permitir cancelar una solicitud Solicitada, sin asignarle número de póliza. | Usuario / Funcional | SIGA 6.1.3, botón «Cancelar»; diagrama de estados (1.3) | Con una solicitud Solicitada, cancelarla la deja Cancelada y sin número. |
| RF-11 | G04-14 | El sistema debe mostrar el estado actual de la solicitud y, tras emitirla, su número de póliza. | Usuario / Funcional | Hallazgo E1-7; diagrama de estados (1.3) | En cada paso el estado mostrado es el correcto; tras emitir se ve el número. |
| RF-12 | G04-15 | Cada productor debe tener usuario propio y poder registrar y emitir una solicitud por sí mismo. | Usuario / Funcional | Acta 3.4 (decisión de A. Pampín); Caso §4 (J. Ponce) | Un productor con su usuario registra, valida y emite el caso base sin intervención de Mesa de Ayuda. |

## Fragmentos que NO son requerimientos funcionales

Para cada fragmento del relevamiento que no calificó como RF, clasificar
según las categorías de `skill/SKILL.md` (objetivo/meta de negocio,
restricción técnica, RNF, dato de contexto) y justificar en una línea
por qué no es un RF.

| Fragmento | Texto | Categoría | Justificación |
|-----------|-------|-----------|----------------|
| Caso §4 (A. Pampín); Acta 4.5 | «Quiero un sistema rápido, moderno y fácil de usar. Que el productor lo pueda usar sin capacitación.» | Requisito no funcional (RNF) | Sin métrica; el acta lo dejó pendiente (equipo propone, Pampín aprueba, 30/10/2026). |
| Caso §4 (A. Pampín); Acta 3.2 | «Quiero que esté antes de que se jubile Héctor.» (sistema operativo el 1/3/2027) | Objetivo/meta de negocio | Es un plazo del proyecto, no una función del sistema. |
| Caso §2 | SIGA desarrollado en 2003 sobre Visual Basic 6 con SQL Server | Dato de contexto | Describe el sistema actual y no pide nada del nuevo. |
| Caso §4 (J. Ponce); §3.2 | «Yo le cotizo el lunes y la póliza sale el jueves» (el circuito demora 24 a 72 horas hábiles) | Dato de contexto | Describe el proceso de hoy; origina RF-03 y RF-12. |
| Caso §4 (S. Roldán) | «Si el cliente ya tiene otra póliza… hasta veinticinco» | Dato de contexto | Práctica informal que el Acta 3.3 dejó sin efecto. |
| Acta 3.1 | Ramos hogar y accidentes personales quedan en SIGA hasta una segunda etapa | Dato de contexto | Delimita el alcance; el frente cubre solo automotores. |

## Conflictos u observaciones detectadas

Si al procesar los fragmentos aparece un conflicto de valores (ver
"Detección de conflictos" en la skill), documentarlo acá aunque no
afecte directamente un RF puntual.

-
