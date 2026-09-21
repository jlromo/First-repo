# Biblioteca de patrones comunes del sector público

Estos cinco patrones cubren la mayoría de los procesos que aparecen en
dependencias de gobierno. Sirven para acelerar el mapeo: en vez de
levantar el proceso completamente desde cero, identifica cuál(es)
patrón(es) se combinan en el caso concreto y úsalos como lista de
verificación de roles y pasos que fácilmente se omiten al describir el
proceso de memoria. Ningún caso real calza perfecto en un solo patrón —
trátalos como puntos de partida, confirma cada elemento con el usuario.

## 1. Aprobación multinivel / jerárquica

**Cuándo aparece**: autorizaciones de gasto, permisos que requieren firma
de más de un nivel, contrataciones, cualquier trámite donde "entre más
grande el monto/impacto, más alto tiene que aprobar".

**Elementos típicos que se olvidan mencionar**:
- Umbrales que determinan cuántos niveles de aprobación se requieren
  (¿es un solo umbral o una escalera de varios?).
- Qué pasa si un nivel intermedio rechaza: ¿regresa al solicitante, se
  archiva, o puede el solicitante apelar al siguiente nivel directamente?
- Mecanismo de suplencia cuando el aprobador titular no está disponible
  (¿existe firma delegada? ¿cuánto se detiene el proceso si no?).
- Si hay un límite de tiempo por nivel, o el reloj del SLA corre sobre
  todo el proceso sin puntos de control intermedios.

**Riesgo característico**: cuellos de botella concentrados en la firma de
la autoridad más alta, que suele ser también la persona con menos
disponibilidad de agenda.

## 2. Gestión de expedientes / trámites

**Cuándo aparece**: cualquier trámite ciudadano o interno que genera un
expediente que se abre, se completa a lo largo de varios pasos, y se
cierra con una resolución (licencias, permisos, registros, solicitudes de
información, denuncias).

**Elementos típicos que se olvidan mencionar**:
- Qué constituye el expediente "completo" para poder iniciarlo
  formalmente (lista de requisitos) vs. qué se puede subsanar después.
- Si existe un número de folio/expediente único y quién lo asigna, y si
  el ciudadano puede darle seguimiento a su estatus de forma autónoma.
- Custodia física vs. digital del expediente, y qué pasa si se traspapela.
- Tiempo de resguardo posterior al cierre (archivo, obligaciones de
  transparencia/acceso a la información sobre ese expediente).

**Riesgo característico**: pérdida o duplicación de información porque el
mismo dato se captura varias veces en distintos sistemas o formularios a
lo largo del expediente.

## 3. Atención y respuesta a ciudadanos

**Cuándo aparece**: ventanillas de atención, líneas de quejas y
denuncias, solicitudes de información, peticiones ciudadanas (derecho de
petición).

**Elementos típicos que se olvidan mencionar**:
- Canales de entrada múltiples (presencial, telefónico, portal web, redes
  sociales) y si convergen en un mismo sistema de seguimiento o quedan
  fragmentados por canal.
- SLA de primera respuesta vs. SLA de resolución final (suelen ser
  distintos y confundirse).
- Mecanismo de escalamiento cuando el ciudadano no está satisfecho con la
  respuesta inicial.
- Cómo se mide satisfacción o calidad de la respuesta, si se mide.

**Riesgo característico**: el ciudadano recibe una respuesta formalmente
a tiempo pero que no resuelve el fondo de su solicitud, porque el
indicador que se mide es "tiempo de respuesta" y no "resolución
efectiva".

## 4. Procesos con validación normativa de documentos

**Cuándo aparece**: cualquier trámite donde un funcionario debe verificar
que documentación cumple requisitos legales antes de continuar
(verificación de identidad, cumplimiento fiscal, requisitos técnicos de
un proyecto, autenticidad de documentos).

**Elementos típicos que se olvidan mencionar**:
- Si la validación es un criterio binario y objetivo, o requiere
  interpretación/juicio del funcionario (esto último es fuente de
  variabilidad e inconsistencia entre casos similares — vale la pena
  señalarlo como hallazgo).
- Si existen listas de verificación (checklists) oficiales o cada
  funcionario valida "a su criterio".
- Consecuencia de un error de validación (¿quién es responsable si se
  aprobó algo que no debía?).
- Si hay verificación cruzada con otro sistema o dependencia (p. ej.
  validar contra un padrón, un registro civil, una base de sanciones).

**Riesgo característico**: inconsistencia entre funcionarios o
ventanillas distintas que aplican el mismo criterio normativo de forma
diferente, generando percepción de arbitrariedad o corrupción aunque no
la haya.

## 5. Procesos interinstitucionales / transferencia de expediente entre dependencias

**Cuándo aparece**: cualquier trámite que requiere la intervención de más
de una dependencia u orden de gobierno (municipal-estatal-federal, o
entre secretarías) antes de resolverse.

**También aplica, como híbrido, dentro de una misma dependencia**: cuando
varias áreas internas (no dependencias distintas) se pasan el expediente
en secuencia sin un sistema compartido ni un dueño único del tiempo total
— por ejemplo, tres direcciones de un mismo municipio que se turnan un
expediente en papel. No es un caso interinstitucional en sentido estricto,
pero tiene el mismo riesgo característico (tiempo "en tránsito" sin dueño
ni medición) y conviene diagnosticarlo con la misma lista de verificación.
Dilo explícitamente en el documento cuando trates un caso así como
híbrido, en vez de forzarlo a encajar en el patrón 1 (jerárquico) o el 2
(expediente) solamente.

**Elementos típicos que se olvidan mencionar**:
- Formato en el que se transfiere el expediente entre dependencias
  (¿sistema integrado, oficio físico, correo electrónico?) — esto casi
  siempre es el punto de mayor pérdida de tiempo del proceso completo.
- Quién es responsable del expediente mientras está "en tránsito" entre
  dependencias (zona gris de responsabilidad).
- Si existe un acuerdo o convenio formal entre las dependencias que
  defina tiempos de respuesta mutuos, o si cada una opera con sus propios
  tiempos sin coordinación.
- Qué pasa si una dependencia rechaza o pausa el trámite: ¿el ciudadano se
  entera directamente, o debe enterarse por la dependencia que inició el
  trámite?

**Riesgo característico**: el tiempo total percibido por el ciudadano es
mucho mayor que la suma de los tiempos internos de cada dependencia,
porque el tiempo "en tránsito" entre ellas no se mide ni se le asigna
dueño.
