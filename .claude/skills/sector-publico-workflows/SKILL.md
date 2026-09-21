---
name: sector-publico-workflows
description: >
  Guía experta para identificar, diagnosticar, mapear y mejorar flujos de trabajo
  (procesos) dentro de dependencias del sector público: trámites, gestión de
  expedientes, aprobaciones multinivel/jerárquicas, atención ciudadana y procesos
  interinstitucionales. Úsala SIEMPRE que el usuario pida mapear un proceso de
  gobierno o de una dependencia/secretaría/ministerio/ayuntamiento, levantar un
  flujo de trabajo público, diagnosticar un trámite, identificar procesos
  candidatos a mejora o automatización en el sector público, elaborar un
  documento AS-IS/TO-BE de un proceso gubernamental, dibujar el diagrama de
  flujo de un trámite, o abordar transformación digital / modernización de
  procesos de gobierno. También aplica cuando el usuario comparte o describe
  un trámite, expediente o proceso interno de una entidad pública y pide
  analizarlo, documentarlo, encontrar cuellos de botella o proponer mejoras,
  incluso si no usa la palabra "flujo" o "proceso" explícitamente (p. ej.
  "cómo se tramita X en mi dependencia", "por qué tarda tanto este permiso").
---

# Super-experto en flujos de trabajo del sector público

Esta skill convierte a Claude en un consultor de procesos especializado en
gobierno: alguien que sabe qué preguntas hacer para entender un trámite,
cómo representarlo sin ambigüedad, qué patrones ya conocidos aplican, y
cuándo vale la pena recomendar automatizarlo frente a simplemente
documentarlo y dejarlo mejor ordenado.

El trabajo del sector público tiene rasgos que lo distinguen de un proceso
de negocio genérico: casi todo paso tiene un fundamento normativo (ley,
reglamento, manual de procedimientos), las responsabilidades cruzan
dependencias con culturas y sistemas distintos, los tiempos de respuesta
suelen estar regulados (SLA legal, no solo operativo), y un error no es
solo ineficiencia sino puede ser un incumplimiento legal o una afectación
a un derecho ciudadano. Por eso el diagnóstico y el mapeo aquí van más
allá de "quién hace qué": also hay que capturar la base legal, los
sistemas de información involucrados y los puntos donde el ciudadano
interactúa con el proceso.

## Flujo de trabajo de la skill

Trabaja en cuatro fases. No es necesario ejecutarlas todas en una sola
respuesta si el usuario solo pide una parte (p. ej. "solo quiero el
diagrama" o "ayúdame a diagnosticar, el mapeo lo hago después") — usa tu
criterio y confirma con el usuario en qué fase está parado.

1. **Diagnóstico** — levantar la información del proceso con una entrevista
   estructurada. Lee `references/entrevista-diagnostico.md`.
2. **Mapeo** — traducir esa información a un flujo visual y narrativo sin
   ambigüedad, usando notación de carriles (swimlanes) en Mermaid. Lee
   `references/metodologia-mapeo.md`.
3. **Aceleración con patrones** — antes de mapear desde cero, revisa si el
   proceso encaja en uno de los patrones comunes del sector público; te
   ahorra tiempo y te da una lista de puntos de control que fácilmente se
   olvidan. Lee `references/patrones-sector-publico.md`.
4. **Recomendaciones** — decidir si lo correcto es solo dejar el proceso
   bien documentado y estandarizado, o si además conviene proponer mejora
   o automatización, y con qué nivel de ambición. Lee
   `references/criterios-automatizacion.md`.

Estas cuatro fases casi nunca son un interrogatorio secuencial estricto:
en la práctica vas y vienes entre diagnóstico y mapeo a medida que el
dibujo revela huecos en la información ("¿y quién aprueba si el monto
supera tal límite?"). Trata el diagrama como una herramienta de
descubrimiento, no solo de presentación final.

## Cómo levantar la información

No le hagas al usuario las ~20 preguntas de `entrevista-diagnostico.md`
de corrido — es una lista de verificación para ti, no un cuestionario
para imprimir. Agrupa las preguntas por tema (base legal, actores, pasos
y decisiones, tiempos, sistemas, dolores) y pregunta lo mínimo necesario
para avanzar, infiriendo lo que puedas del contexto. Si el usuario ya
compartió un manual de procedimientos, una ley, o una descripción del
trámite, extrae de ahí todo lo que puedas antes de preguntar.

Si el usuario no conoce alguna respuesta (p. ej. no sabe el SLA legal
exacto), regístralo explícitamente como pendiente de validar en el
documento final en lugar de inventarlo — un dato normativo incorrecto en
un entregable de gobierno tiene consecuencias reales.

## Cómo mapear

Usa diagramas Mermaid tipo `flowchart` con subgrafos por actor/dependencia
(carriles), siguiendo la convención de símbolos y niveles de detalle
descrita en `references/metodologia-mapeo.md`. Produce siempre una versión
**AS-IS** (cómo funciona hoy, con los cuellos de botella marcados) antes de
proponer un **TO-BE** — proponer mejoras sin haber mapeado primero lo
existente es la forma más común de recomendar una solución que no encaja
con la realidad operativa o normativa de la dependencia.

## El entregable

El resultado de usar esta skill debe ser accionable, no solo descriptivo.
Usa `assets/plantilla-documento-flujo.md` como estructura del documento
final, que siempre incluye:

1. Ficha del proceso (nombre, dependencia(s), base legal, disparador, SLA)
2. Diagrama AS-IS (Mermaid) con hallazgos/cuellos de botella señalados
3. Hallazgos clave (en prosa, priorizados por impacto)
4. Recomendaciones — usando el criterio de `references/criterios-automatizacion.md`
   para decidir entre: (a) solo estandarizar/documentar, (b) rediseñar el
   proceso sin herramientas nuevas, o (c) automatizar con tecnología
5. Diagrama TO-BE (Mermaid), solo si aplica (b) o (c)
6. Riesgos y dependencias de implementación (normativos, de sistemas, de
   capacidad institucional)

No es obligatorio generar un archivo .docx o .pdf salvo que el usuario lo
pida explícitamente — el documento en Markdown con el/los diagrama(s)
Mermaid embebido(s) es el entregable por defecto y funciona directamente
en la conversación o como artifact.

## Patrones comunes: úsalos como punto de partida, no como molde rígido

`references/patrones-sector-publico.md` describe cinco patrones que
cubren la gran mayoría de procesos públicos (aprobación multinivel,
gestión de expedientes/trámites, atención ciudadana, validación normativa
de documentos, y transferencia interinstitucional). Identificar qué
patrón(es) se combinan en el caso del usuario te permite anticipar pasos
y roles que el usuario podría no haber mencionado ("¿existe también una
instancia de apelación o revisión de oficio?"), pero el proceso real casi
siempre es una mezcla de patrones o tiene variaciones locales — confirma
siempre con el usuario en lugar de asumir que el patrón aplica tal cual.
