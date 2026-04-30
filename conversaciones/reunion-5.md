# Reunión 5 — Refinamiento Final del Orquestador + Construcción del Prompt

**Meeting date:** 13 de abril
**Grabación Fathom:** https://fathom.video/share/n-yK8SHgspCtykZ21yby49EfcSeWe2_4
**Duración:** 57 min
**Participantes:** Andres Linares, Carlos Valerin (Christian no estuvo presente)

---

## Contexto de la reunión

Andres ya había generado un documento "BOT ORQUESTADOR — CV FINANZAS" basado en las 4 reuniones previas. Carlos lo revisó, hizo comentarios. Esta reunión integra esos cambios y construye el prompt final para GHL.

---

## Cambios validados/agregados durante la reunión

### Fase 0 — Activación (palabras disparadoras)
- ✅ "finanzas" — la principal
- ✅ Se pueden agregar más (ej: "EXPO" para feria de autos cuando lanzan campañas específicas)
- Andres dejará un video de cómo cambiar/agregar palabras clave en GHL

### Outbound — ManyChat
- Para nuevos seguidores → usar **ManyChat plan gratuito**
- ManyChat dispara → entra en GHL como cualquier otro lead

### Fase 1 — Saludo (alternativa)
Christian sugirió como variación del saludo:
> *"...algo en particular que te llamó la atención?"*

Ambas opciones válidas, se pueden rotar.

### Fase 3a — Pregunta clave (REESCRITA por Carlos para tono "tico")

Versión final acordada:
```
¿Qué te interesaría más a vos?
- ¿Rentabilizar unos ahorros que tenés disponibles?
- ¿Generar ahorros que trabajen para vos?
- ¿Hacer una revisión de algún producto (como hipoteca o crédito prendario) que ya hayas adquirido o que estés evaluando?
- ¿O te gustaría aprender a gestionar tu dinero vos mismo?
```

**Cambios respecto a versión Christian:**
- Reemplazado "rentabilizar" por "rentabilizar unos ahorros que tenés disponibles" (más explícito)
- Agregada nueva opción: **"Generar ahorros que trabajen para vos"**
- Agregados ejemplos en revisión: hipoteca, crédito prendario

### Fase 3c — Contexto financiero (AGREGADO por Carlos)
Pregunta nueva a hacer:
> *"¿Tenés el hábito del ahorro?"*

### Fase 4 — Sesión de claridad
Decisión: por ahora el bot **levanta la mano a Christian** y él califica si el lead pasa el corte de USD 1.500 mensuales. La encuesta/cuestionario solo se implementa cuando haya volumen excesivo que justifique automatizarlo.

### Fase 5 — Speeches REESCRITOS por Carlos

**Speech asesoría $100 (NUEVO):**
```
En el caso que me comentás, lo que haríamos sería una sesión de una hora por
videollamada que tiene un costo de USD 100 + IVA. En la llamada revisaremos
tu perfil, tus objetivos, tolerancia de riesgo entre otros y revisaremos las
opciones que se apegan a tu realidad financiera.

Dependiendo de nuestra reunión podremos tener revisiones periódicas y acceso
a mis consultas según tu necesidad.

El acompañamiento es SIN COSTO una vez que adquirís el servicio.
```

**Speech revisión $150 (NUEVO — sin revisiones ni consultas gratis):**
```
En el caso que me comentás, vamos a ir directo al grano a ver tus
posibilidades según tus objetivos. Esta reunión tiene un costo de USD 150 + IVA,
es un pago único para revisar el producto que ya tenés y ver cómo lo podés
gestionar de la mejor manera.

¿Qué te parece esta opción?
```

⚠️ **Diferenciador clave (recuadro azul):**
El acompañamiento SIN COSTO **solo aplica para asesoría financiera ($100)**, NO para revisión de productos ($150). El bot nunca debe prometerlo en revisión.

### Seguimiento — regla reforzada
- Christian flaggeó: el bot repetía el mismo mensaje de seguimiento
- **Regla:** cada seguimiento debe ser DIFERENTE
- La IA del bot lee la conversación y genera mensaje contextual (NO usar mensaje predefinido)

---

## Construcción del Prompt del Bot (estructura final)

Andres armó el prompt siguiendo las mejores prácticas de **AI Prompting 101 de GHL**:

### Estructura en 3 secciones
1. **Personalidad** — quién es el bot, tono, regulaciones
2. **Objetivo** — qué busca lograr (perfilar + derivar a uno de 4 destinos)
3. **Información adicional** — destinos, reglas, vocabulario, casos extremos

### Patrones aplicados
- **Repetición intencional** de reglas críticas (no "inversión", no consejos) en personalidad + objetivo + info adicional
- **Ejemplos buenos vs malos** con "evitar / usar"
- **Delimiters XML** para separar bloques (flujo, destinos, reglas, vocabulario)
- **Contexto cultural** al inicio (tema tabú de finanzas en Costa Rica)

### Custom values usados
- `{{custom_values.link_libro}}` — link al libro de Carlos para mensajes de descarte

---

## 6 escenarios de Human Handover configurados en GHL

Importante: **los handovers solo se activan DESPUÉS del paso 5** (cuando el bot ya tiene certeza del destino post-perfilamiento). Nunca antes.

| # | Escenario | Color | Acción |
|---|-----------|-------|--------|
| 1 | Asesoría financiera | Azul | Transfer a Christian — listo para enviar Calendly |
| 2 | Revisión de productos | Amarillo | Transfer a Christian — listo para enviar Calendly |
| 3 | Sesión de claridad | Verde | Transfer a Christian — calificar manualmente |
| 4 | Libro | Rojo | Mandar link libro + tag "no calificado" |
| 5 | Levantar la mano (caso ambiguo) | Violeta | Christian decide |
| ~~6~~ | ~~Solicitud directa de humano~~ | — | ELIMINADO — si pide humano antes del paso 5, el bot insiste con preguntas |

---

## Decisiones que reseteó Carlos

- ❌ NO usar palabra "inversión" (NUNCA, ni siquiera como sustantivo en frases tipo "productos de inversión")
- ✅ Bot debe sonar "tico" (no argentino) — Carlos reescribió las preguntas
- ✅ Acompañamiento SIN COSTO debe quedar CRISTALINO en cada speech de asesoría

---

## Pendiente para próxima reunión

- [ ] Christian valida el prompt final del orquestador
- [ ] Cargar prompt en GHL
- [ ] Testear con casos reales (capturas)
- [ ] Iterar pulgares arriba/abajo
- [ ] Activar bots de destino (asesoría/revisión/claridad) cuando orquestador esté pulido
