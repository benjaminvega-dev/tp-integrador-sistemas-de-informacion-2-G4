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
| RF-05 | | |

## Fragmentos que NO son requerimientos funcionales

Para cada fragmento del relevamiento que no calificó como RF, clasificar
según las categorías de `skill/SKILL.md` (objetivo/meta de negocio,
restricción técnica, RNF, dato de contexto) y justificar en una línea
por qué no es un RF.

| Fragmento | Texto | Categoría | Justificación |
|-----------|-------|-----------|----------------|
| | | | |
| | | | |

## Conflictos u observaciones detectadas

Si al procesar los fragmentos aparece un conflicto de valores (ver
"Detección de conflictos" en la skill), documentarlo acá aunque no
afecte directamente un RF puntual.

-
