# CV Finanzas

Cliente de **AL Consulting**. Educación financiera + asesoría / inversión / ahorro / hipoteca.

**País:** Costa Rica
**Web:** cvfinanzas.com
**Cómo llegó:** referido por **Javier Raaz**

## Equipo CV Finanzas

| Persona | Rol |
|---------|-----|
| **Carlos Valerin** | Dueño + Closer (cvfinanzas.com) |
| **Christian** | Setter (argentino, Córdoba) |
| **Emi** | Manejo de información de clientes / seguimiento |
| **Javier Raaz** | Referente del proyecto a Inflect |

## Equipo AL Consulting

- **Andrés Linares** — implementación GHL

## Productos / servicios

- **Asesoría financiera** (sesiones suelta)
- **Revisión productos financieros** ($150 USD) — para clientes con producto ya adquirido (hipoteca, inversión) que quieren segunda opinión
- **Programa** — sesión de claridad inicial → educación financiera completa (ahorra/invierte)
- **Libro** — entry-level / descarte para no calificados endeudados
- **Hipoteca** — revisión de propuestas hipotecarias (3 propuestas, etc.)

## Stack actual (que están reemplazando)

- **Excel** — planilla manual de tracking (Christian, inbound)
- **Notion** — base de clientes activos (Carlos, contactos cada 6 meses, módulos del programa)
- **Skool** — plataforma de cursos (a migrar a GHL)
- Han pasado por **Excel → Monday → Notion** y perdieron info en cada migración

## Dolor principal identificado

- Carlos tiene que ir a buscar conversaciones manualmente porque la gente en redes no se llama por su nombre real
- Christian responde a las 10pm CR (1am Argentina) — necesita bot que cubra horarios fuera de oficina
- Sin visibilidad cruzada entre redes (Instagram, FB, TikTok, WhatsApp)
- Cuando cambia el sistema (Excel → Monday → Notion → ...) pierden info histórica

## Insights críticos del lenguaje (Christian)

> ⚠️ **"Inversión" es palabra prohibida** — usar siempre **"rentabilizar dinero"** o **"rentabilizar ahorros"**. Inversión genera resistencia.

## Bot debe ser ULTRA humanizado

- Christian usa errores ortográficos a propósito + emojis (corazoncitos, deditos)
- Mucha gente reconoce bots → desconectan al detectarlo
- Audio (en WhatsApp) clave para reforzar humanidad

## Arquitectura propuesta — Multi-bot

1. **Bot orquestador** = filtra/perfila → identifica qué producto encaja
2. **Bot por producto** = vende ese producto específico
3. Cada producto tiene su **pipeline** (tubería) separado en GHL

## Recurso visual del cliente

**Miro board** mostrado en la reunión — mapeo de productos + bots + filtros:
- Bot orquestador con disparador "finanzas"
- Bot orquestador → 3 ramas: asesoría, revisión, programa
- Filtros visualizados: "a qué te dedicas", "capacidad de ahorro"
- Tally como herramienta de formulario para cuestionarios complejos
- Productos con código de color (asesoría, hipoteca, revisión, sesión de claridad, programa, libro)

## Conversaciones importadas (5 reuniones)

- [reunion-1.md](./conversaciones/reunion-1.md) — **15 ene** — Presentación CRM al equipo + perfilado de productos + primeros filtros (69 min)
- [reunion-2.md](./conversaciones/reunion-2.md) — **4 mar** — Avance estructural + setup bot sesión claridad + Google Docs como base de conocimiento (72 min)
- [reunion-3.md](./conversaciones/reunion-3.md) — **5 mar** — Deep dive con Christian solo + setup como usuario + lógica real de filtrado (39 min)
- [reunion-4.md](./conversaciones/reunion-4.md) — **9 abr** — ⚠️ **CRÍTICA**: bot derivando MAL → reseteo de estrategia, retroceder a "solo orquestador + levantar mano" (56 min)
- [reunion-5.md](./conversaciones/reunion-5.md) — **13 abr** — Refinamiento final del orquestador + speeches definitivos + construcción del prompt (57 min)

## Knowledge / Deliverables

- [bot-orquestador-cv-finanzas.md](./knowledge/bot-orquestador-cv-finanzas.md) — **DOCUMENTO MAESTRO v3** consolidando todas las decisiones para implementar el bot en GHL (filtros, speeches, reglas, ejemplos, prohibiciones)

## Recursos externos (Fathom recordings)

- **R1 (15 ene):** https://fathom.video/share/zkwVnWb7fmsE5hCXxEjWJoPmRyZnk7oX
- **R2 (4 mar):** https://fathom.video/share/-s-qMpENNixPN3vTBNYsr8mRKH5XeCCu
- **R3 (5 mar):** https://fathom.video/share/1ZH4b7X6yFJpVHJE9X7T4vG6avqYvtvo
- **R4 (9 abr):** https://fathom.video/share/ZMzkMFXPdetsFtLs8dLU8vF_mGcoc5ib
- **R5 (13 abr):** https://fathom.video/share/n-yK8SHgspCtykZ21yby49EfcSeWe2_4

## Estado actual (post Reunión 5)

✅ Bot orquestador con prompt completo armado siguiendo AI Prompting 101 de GHL
✅ 6 escenarios de Human Handover configurados (con regla: solo activar post-paso 5)
✅ Custom value `{{custom_values.link_libro}}` integrado para el descarte suave
✅ Speeches finales validados por Carlos
🔄 Pendiente: Christian valida prompt → cargar en GHL → testeo con casos reales
🔒 Bots de destino (asesoría/revisión/claridad) **temporalmente apagados** hasta que orquestador esté pulido

## Pendientes / próximos pasos

- [ ] Definir estructura completa de filtros para los 4 productos (no solo asesoría)
- [ ] Definir pipelines por producto en GHL
- [ ] Christian pasa transcripts/conversaciones reales para que Andres pueda iterar el bot
- [ ] Carlos + Emi: definir info que necesitan trackear de cada cliente (familia, hijos, estado, módulo del programa)
- [ ] Migrar contactos de Notion a GHL
- [ ] Plan a largo plazo: migrar cursos de Skool a GHL para tracking automatizado de progreso

## Patrones especiales requeridos

### Recontacto automático cada 6 meses
Para clientes activos. Si no agendan después de N intentos → escalar a Carlos/Christian con notificación interna.

### Notas de contexto personal en cada contacto
Para venta cruzada — ej: cliente Andrés tiene hija Lía (5 años) → en 1 año puede venderle seguro de vida.

### Track de progreso del programa
Cuando lead compra el programa: track de módulo actual + automatización por hito (módulo 1 completado → mensaje X, módulo 3 → mensaje Y).
