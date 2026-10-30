# Requerimientos

Completar a partir de los fragmentos de relevamiento del caso. Seguir
la convención de `skill/SKILL.md` (atómico, verificable, sin tecnología
mezclada).

Frente 2 · Emisión de pólizas de automotor · Grupo G04. Convención de `skill/SKILL.md`: atómico, verificable, sin tecnología mezclada. Misma tabla que la 2.2 del informe (se agregaron las columnas de issue, nivel y tipo, y criterio).

## Requerimientos funcionales

| ID | Requerimiento | Fragmento(s) de origen |
|----|---------------|--------------------------|
| RF-01 | G04-2 | El sistema debe registrar una solicitud de emisión de póliza de automotor para un cliente y un vehículo ya registrados, con el año del vehículo, el valor asegurado, los datos del riesgo (cobertura RC, TC o TR; edad del conductor; zona de radicación; siniestros de los últimos 24 meses; guarda en garaje) y las condiciones comerciales (débito automático, otra póliza vigente, antigüedad del cliente), y dejarla Solicitada. [NEEDS CLARIFICATION: los valores posibles de la zona de radicación no figuran en el caso ni en el acta. Decide R. Ferreyra.] | Usuario / Funcional | SIGA 6.1.3 «Emisión de pólizas»; Caso §2.1 (alta de cliente y de vehículo), §3.2 (paso 3) y §6 (coberturas); hallazgo E2-1 | Con los datos completos la solicitud queda Solicitada; si falta alguno, no se registra. |
| RF-02 | | |
| RF-03 | | |
| RF-04 | | |
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
