# Cuándo recomendar automatización o mejora, y cuándo no

No todo diagnóstico debe terminar en una recomendación de automatizar.
Recomendar tecnología cuando el problema real es de coordinación,
claridad normativa o simple falta de estandarización es un error común
que además suele ser costoso y lento de implementar en gobierno. Usa esta
jerarquía, en orden: intenta resolver con la opción más simple que de
verdad ataque la causa raíz antes de subir al siguiente nivel.

## Nivel 1 — Solo estandarizar y documentar

**Recomiéndalo cuando** el problema principal identificado en el
diagnóstico es que el proceso no está escrito en ningún lado, cada
funcionario lo hace un poco distinto, o el manual existe pero está
desactualizado respecto a la práctica real. El síntoma típico es
variabilidad entre personas o turnos, no lentitud estructural.

**Qué se entrega**: el documento AS-IS mismo, convertido en el nuevo
procedimiento oficial, más una checklist operativa corta que el personal
pueda usar en el día a día. Bajo costo, bajo riesgo, e implementable en
semanas sin depender de presupuesto de TI.

## Nivel 2 — Rediseñar el proceso sin nueva tecnología

**Recomiéndalo cuando** el diagnóstico muestra pasos redundantes,
aprobaciones innecesarias, validaciones duplicadas entre áreas, o un
orden de pasos que podría reorganizarse (p. ej. hacer en paralelo lo que
hoy es secuencial, o eliminar un nivel de revisión que nunca rechaza
nada). Es decir: el problema está en el *diseño* del proceso, no en la
falta de una herramienta.

**Qué se entrega**: el diagrama TO-BE mostrando específicamente qué pasos
se eliminan, fusionan o paralelizan respecto al AS-IS, y por qué cada
cambio es seguro (qué control se pierde, si alguno, y por qué es
aceptable perderlo). Esta es la recomendación con mejor relación
costo/impacto en la mayoría de los diagnósticos de gobierno — vale la
pena agotarla antes de proponer tecnología nueva.

## Nivel 3 — Automatizar con tecnología

**Recomiéndalo solo cuando** además de lo anterior, el diagnóstico
muestra evidencia concreta de al menos una de estas señales:

- Captura manual repetida del mismo dato en múltiples sistemas o
  formularios (indicador claro de que la integración de sistemas
  resolvería el problema, no solo el rediseño del proceso).
- Alto volumen del trámite, donde incluso una pequeña reducción de tiempo
  por caso genera un ahorro agregado significativo.
- Reglas de decisión objetivas y estables (no sujetas a juicio caso por
  caso) que se podrían codificar — por ejemplo, un cálculo de elegibilidad
  basado en umbrales claros.
- Necesidad de trazabilidad/auditoría que un proceso en papel o correo no
  puede garantizar de forma confiable.

**Qué se entrega**: además del TO-BE, una nota de alcance que distinga
claramente entre digitalizar lo existente (mover el mismo proceso a un
sistema, ganancia moderada) y automatizar decisiones (el sistema resuelve
casos simples sin intervención humana, ganancia mayor pero requiere
reglas de negocio muy claras y suele exigir cambio normativo si la ley
exige firma/revisión humana explícita).

## Una advertencia importante sobre gobierno específicamente

Antes de proponer Nivel 2 o 3, verifica explícitamente si alguno de los
pasos que planeas eliminar, fusionar o automatizar está *mandatado por
ley* (no solo por práctica interna). Eliminar una revisión que la norma
exige, aunque parezca redundante operativamente, no es una mejora — es un
incumplimiento. Cuando tengas dudas sobre si un paso es legalmente
obligatorio, dilo explícitamente en el entregable como algo a validar con
el área jurídica de la dependencia, en vez de asumir en cualquier
dirección.

## Cómo comunicar el nivel recomendado

En el documento final, justifica el nivel elegido en una o dos frases
ligadas directamente a un hallazgo del diagnóstico ("se recomienda Nivel
2 porque el 80% del tiempo del trámite se pierde en dos revisiones
secuenciales que no interactúan entre sí y podrían correr en paralelo"),
no como una preferencia genérica por lo digital. Si el usuario pidió
explícitamente una propuesta de automatización, puedes describir cómo se
vería el Nivel 3, pero sé honesto si el diagnóstico no sustenta que sea
la prioridad — señala igual las mejoras de Nivel 1 y 2 que darían
resultado más rápido.
