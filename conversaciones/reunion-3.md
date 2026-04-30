# Reunión 3 — Deep Dive con Christian + Setup como Usuario

**Meeting date:** 5 de marzo
**Grabación Fathom:** https://fathom.video/share/1ZH4b7X6yFJpVHJE9X7T4vG6avqYvtvo
**Duración:** 39 min
**Participantes:** Andres Linares, Christian Schmid (sin Carlos)

---

## Objetivo

Andres + Christian solos para extraer la lógica REAL de filtrado del bot orquestador. Christian es el setter humano cuya lógica el bot tiene que replicar.

---

## El mensaje inicial estandarizado (acordado)

```
Hola [nombre], aquí Carlos, gusto en saludarte.
¿Querés que comentemos algo en especial sobre tus finanzas?
```

**Notas:**
- Verificación de español neutro hecha (no "comentemos" rioplatense)
- Versión válida también: *"vi que comentaste mi publicación, contame un poco más"*

### Por dónde se activa
- Cuando comentan **finanzas** en un post → DM automático
- Cuando ponen **finanzas** en una historia → DM automático
- ⚠️ **Christian aclaró:** Carlos tiene MUCHOS amigos pero el 96% comenta "finanzas" → palabra disparadora válida

---

## Cómo Christian filtra MANUALMENTE

### Ejemplo real (Sofia Galvez)
- Persona suelta: "tengo 2 apartamentos, renta, tengo el quilombo en dólar"
- Christian detecta: tiene activos, pero coyuntura económica
- Estrategia: cuando se estabilice → ofrecer rentabilizar ahorros
- Tag: **futuro lead asesoría financiera**

### Ejemplo real (Max Alvarado)
- Comentó por finanzas
- Pregunta: *"recibimos parte de ingresos en dólares. ¿Vos podrías asesorarnos qué hacer con el TZ tan bajo?"*
- Christian: *"¿A vos te interesaría rentabilizar esos ahorros?"*
- Suelta: *"sí, recibimos en dólares + ingresos en dólares"*
- **Tipo:** Asesoría financiera

### Speech estandarizado de Christian para asesoría ($100)
```
Vamos a ir directo al grano a ver las mejores opciones.
Es un pago único. Una vez que hayamos hecho la movida que tenemos que hacer,
vamos a seguir evaluando cada cierto tiempo las decisiones tomadas, y además
vos me podés consultar todo lo que vos quieras, sin costo.
¿Qué te parece esta opción?
```

> Andres: *"este speech debería ser fijo en el bot"*

---

## Lógica del bot orquestador — qué pregunta hacer

### Pregunta clave central (validada con Christian)
```
¿A vos te gustaría más:
- Rentabilizar tus ahorros?
- Hacer una revisión de algún producto que ya tenés adquirido?
- O aprender a gestionar vos mismo tus finanzas?
```

### Lógica de derivación

| Respuesta | Destino |
|-----------|---------|
| Rentabilizar ahorros | **Asesoría financiera** |
| Revisión de producto adquirido | **Revisión de productos** ($150) |
| Aprender a gestionar finanzas | **Sesión de claridad** |
| Tiene mucha deuda + bajos ingresos | **Libro** (descarte/entry) |

### Pregunta de filtro adicional (sutil)
> *"Por cierto, ¿a qué te dedicás?"* ← Christian la usa SIEMPRE para perfilar capacidad económica indirectamente.

### Pregunta backup cuando no suelta info
> *"¿Querés contarme un poquito más de vos, así entro en contexto y ver cómo te puedo ayudar?"*

---

## ⚠️ Reglas críticas de tono (para el bot)

### Palabras prohibidas
- **"INVERSIÓN"** → siempre prohibida (regulatoria) → usar **"rentabilizar dinero/ahorros"**

### Tono
- NO opciones A/B/C — la gente detecta bot al toque
- NO presentarse al inicio — el bot debe ser ULTRA humano
- Una pregunta al final SIEMPRE (mania de Christian: no dejar conversación abierta)

### Test de calidad
- Si el bot suena a libreto → reescribir
- Si suena a Christian conversando → ✅

---

## Iteración del bot

### Christian va a estar a cargo de la iteración
- Bot accesible vía: "Test Your Bot" en cada bot del CRM
- Pulgar abajo + edición + Train Bot
- *"Se equivoca una sola vez"*

### Volumen estimado
- Christian responde a la 1am de Argentina cuando Carlos sube algo
- Volumen alto → "en 2 semanas debería estar al 70%"

---

## Christian agregado como usuario

### Setup ejecutado
- Email: `christian1313@gmail.com`
- Contraseña: `Christian13*`
- Rol: Administrador
- Teléfono: 351 38 60 461
- Acceso a la plataforma + app móvil

---

## Próximos pasos

- [ ] Andres: ajusta el bot orquestador con todo este contexto
- [ ] Andres: deja el bot listo el fin de semana para que Christian lo pruebe
- [ ] Christian: testea desde "Test Your Bot" como si fuera diferentes leads
- [ ] Christian: pasa capturas/feedback por WhatsApp si algo está mal
- [ ] Próxima reunión: cuando esté pulido el orquestador

---

## Filosofía de Christian sobre el bot (frase clave)

> *"El que está escribiendo no es ni el bot, no es ni Christian. Es Carlos Valerín. Un chabón que está todo el tiempo ocupado y no para. Entonces no me puedo poner a escribir muchas caritas, a ser tan vueltero. ¿Querés que comentemos algo sobre finanzas? ¿Qué te llama la atención? Bueno, mira, ayudame a entender un poquito más tu situación, ponerme más en contexto. Listo, largaron todo."*

→ El bot debe sonar **profesional pero ocupado, ágil, sin vueltas, eficiente**.
