# Reunión 2 — Avance Estructural + Setup del Bot de Sesión de Claridad

**Meeting date:** 4 de marzo
**Grabación Fathom:** https://fathom.video/share/-s-qMpENNixPN3vTBNYsr8mRKH5XeCCu
**Duración:** 72 min
**Participantes:** Andres Linares, Carlos Valerin, Javier Raaz (intermitente — se le interrumpe el mecánico)

---

## Avance pre-reunión

Andres preparó:
- ✅ Bot de **sesión de claridad** armado
- ✅ Bot de **asesoría financiera** armado, con calendarios y agenda
- 🔄 Bot de **revisión de productos** falta (necesita base de conocimiento de Carlos)

---

## Definición clave — Perfil ideal de Sesión de Claridad

### Quien LLEGA típicamente
> Persona endeudada (USD 10–20K en deudas), tarjetas, préstamos, no le alcanza fin de mes, no ahorra.

### El "nice to have" (perfil ideal)
- Ingresos **+USD 5.000/mes** (mayor a 5k, ideal)
- Evalúa hasta **USD 3.000/mes**
- Deudas pero **deudas buenas** (carro/casa) — Carlos enseña qué adelantar
- Si tiene tarjeta de crédito chica ($1-2K) → ayuda a salir
- No ahorra constantemente → enseña hábito

### Corte duro: <USD 1.500/mes → Tally
Si la persona gana menos de USD 1.500/mes → **Christian le tira el formulario de Tally** (porque el programa vale USD 1.500, no le va a alcanzar ni en 3 pagos).

---

## Configuración de base de conocimiento — Google Docs

### Decisión arquitectónica
Andres recomienda usar **Google Docs en cuenta de Carlos** (no de Andres) → para que el cliente sea dueño de la data.

### Flujo técnico
1. Crear Google Doc con la info del producto (asesoría / claridad / revisión)
2. Setear como **editor abierto / cualquiera con el link**
3. En GHL: AI Agents → Base de Conocimiento → "Add Source" → "Web Crawler Extract URL"
4. Pegar link del Google Doc
5. **Auto-actualización diaria** activada → cada vez que Carlos edite el Doc, el bot lo lee al día siguiente

### Ventaja crítica
> Si Carlos actualiza el Doc, el bot tiene la última info **automáticamente**. No hay que tocar el bot.

---

## Sistema de iteración del bot

### Cómo iterar
- Cada bot tiene "Test Your Bot" en el panel del bot
- Cuando responde → Pulgar arriba/abajo
- Editar la respuesta correcta
- "Train Bot" → el bot **NUNCA se equivoca dos veces con la misma pregunta**
- Lo aprendido se guarda en la base de conocimiento del bot asociado

### Cosa importante
- Cada respuesta tiene 2 estrellitas a la izquierda → indica **qué bot respondió**
- Si tocás → ves el prompt completo + historial del chat + base usada

---

## Estado del Tally como pre-filtro

Andres preguntó: "¿Cuál es el filtro antes de mandar Tally?"

**Respuesta:** subjetivo, depende del criterio de Christian. Si él tiene dudas, manda Tally; si no, manda directo a sesión.

### Decisión
Por ahora se mantiene la lógica subjetiva. Eventualmente se puede objetivar si volumen lo justifica.

---

## Pipeline en GHL — Movimiento automático de oportunidades

### Cómo funciona
- Lead nuevo entra → aparece en columna "Leads nuevos"
- Si el bot detecta agendamiento → **auto-mueve** a "Agenda sesión claridad" (o donde corresponda)
- El sistema avisa a Carlos por notificación

### Configuración pendiente
Andres va a filtrar por palabra "asesoría" o "finanzas" para que solo entren los relevantes (hoy entran todos los nuevos).

---

## Conexión de Instagram + Detalle del WhatsApp

### Instagram
- Activo, con palabra "finanzas" como trigger
- Si comenta "finanzas" en un post → DM automático
- Si manda DM con palabra "finanzas" → activa el bot de bienvenida (espera 1 minuto antes de responder, para no parecer demasiado bot)

### WhatsApp
- **Aún no conectado** por costos
- Más práctico que Instagram (audio, captura de teléfono y email automáticos)
- Eventualmente: campañas a WhatsApp

### Detalle visual
> *"Por qué siempre me sale aquí Carlos Valerín Coach Financiero?"* — Carlos preguntó. Es solo por la cuenta de Instagram, NO lo ve el cliente.

---

## Audio en WhatsApp

> Andres: *"Tenemos muy buena tasa con audios. La gente escucha audios mucho más que lee texto."*

Cuando se conecte WhatsApp → mandar audios pre-grabados de Carlos en automatizaciones.

---

## Pendientes al cierre

- [ ] Carlos: poblar las bases de conocimiento (Google Docs por bot)
- [ ] Andres: terminar el bot de revisión de productos
- [ ] Carlos: probar los bots desde "Test Your Bot" e iterar
- [ ] Próxima reunión: viernes (juntar a Christian) para terminar el orquestador
