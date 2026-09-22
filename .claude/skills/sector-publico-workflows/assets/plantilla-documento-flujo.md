# Plantilla del documento de flujo de proceso

Usa esta estructura como esqueleto del entregable final. Rellena cada
sección con la información real del caso; elimina o marca como "No
aplica" las subsecciones que de verdad no correspondan, pero no elimines
secciones completas solo para acortar el documento — cada una responde a
una pregunta que el lector (un director, un equipo técnico, un órgano de
control) probablemente va a hacer.

Si el proceso es corto y lineal y decidiste usar una lista de pasos en
vez de un diagrama Mermaid (ver "Cuándo NO usar un diagrama" en
`references/metodologia-mapeo.md`), renombra los encabezados "Diagrama
AS-IS" / "Diagrama TO-BE" a "Descripción del proceso (AS-IS)" /
"Descripción del proceso (TO-BE)" y sustituye el bloque ```mermaid``` por
la lista numerada — el resto de la estructura (ficha, hallazgos,
recomendaciones, riesgos, pendientes) se mantiene igual.

---

# [Nombre del proceso]

## 1. Ficha del proceso

| Campo | Detalle |
|---|---|
| Dependencia(s) involucrada(s) | |
| Disparador | |
| Base legal / normativa | |
| SLA (plazo normado) | |
| SLA real observado | |
| Volumen aproximado (casos/mes o año) | |
| Dueño del proceso | (o "no identificado" si nadie tiene visibilidad end-to-end) |

## 2. Diagrama AS-IS

```mermaid
flowchart TD
    %% diagrama del proceso actual, con carriles por actor/dependencia
```

**Cuellos de botella identificados:**

- [Descripción del cuello de botella 1 — dónde ocurre, cuánto tiempo
  aproximado cuesta, por qué ocurre]
- [Cuello de botella 2]

## 3. Hallazgos clave

Prioriza por impacto, no por orden cronológico del proceso. Para cada
hallazgo, liga explícitamente a qué parte del diagrama corresponde.

1. **[Hallazgo 1]** — [explicación breve y su impacto: tiempo, riesgo
   legal, experiencia ciudadana, costo]
2. **[Hallazgo 2]**
3. **[Hallazgo 3]**

## 4. Recomendaciones

Indica el nivel recomendado (ver `references/criterios-automatizacion.md`)
y justifícalo con un hallazgo concreto de la sección anterior.

| # | Recomendación | Nivel (documentar / rediseñar / automatizar) | Hallazgo que atiende | Esfuerzo estimado |
|---|---|---|---|---|
| 1 | | | | |
| 2 | | | | |

## 5. Diagrama TO-BE

*(Incluir solo si se recomendó Nivel 2 o Nivel 3. Mantener la misma
convención de carriles que el AS-IS para que el cambio sea visualmente
comparable.)*

```mermaid
flowchart TD
    %% diagrama del proceso propuesto
```

**Qué cambia respecto al AS-IS y por qué es seguro hacerlo:**

- [Cambio 1 — qué se elimina/fusiona/paraleliza, y qué control se
  pierde si acaso, y por qué es aceptable]

## 6. Riesgos y dependencias de implementación

- **Normativos**: [¿algún paso propuesto para eliminar o modificar podría
  chocar con un requisito legal? ¿requiere validación jurídica o incluso
  cambio normativo antes de implementarse?]
- **De sistemas**: [¿depende de un sistema legado, de una integración que
  no existe hoy, de presupuesto de TI?]
- **De capacidad institucional**: [¿requiere capacitación, cambio de
  responsabilidades entre áreas, resistencia al cambio anticipable?]

## 7. Pendientes de validar

Lista explícita de cualquier dato que no se pudo confirmar durante el
diagnóstico (p. ej. un SLA legal exacto, un volumen preciso) para que
quede claro qué del documento es información verificada y qué es
estimación o supuesto a confirmar con la dependencia.

- [Pendiente 1]
