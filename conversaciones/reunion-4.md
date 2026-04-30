# Reunión 4 — Iteración Crítica del Bot ("derivando demasiado rápido")

**Meeting date:** 9 de abril
**Grabación Fathom:** https://fathom.video/share/ZMzkMFXPdetsFtLs8dLU8vF_mGcoc5ib
**Duración:** 56 min
**Participantes:** Andres Linares, Carlos Valerin, Christian Schmid, Javier Raaz

---

## ⚠️ Esta reunión es la MÁS IMPORTANTE para el bot

El bot estaba activo y derivando, pero MAL. Carlos + Christian dieron feedback crítico que reseteó la estrategia.

---

## Problema #1 — Calendly mostraba horarios bloqueados

**Síntoma:** El bot ofrecía horarios que estaban bloqueados en el calendario real de Carlos (jueves 100% bloqueados, almuerzos en Costa Rica, etc.)

**Causa:** Andres no había vinculado bien el calendario.

**Solución:** Andres ya lo ajustó en vivo.

---

## Problema #2 — Bot derivando MAL (perfil incorrecto)

### Caso real reportado por Carlos
> *"Ayer teníamos un perfil ayer o antier — Una persona suelta y dice: 'gano [no sé] miles de dólares al mes, mis gastos fijos son tantos al mes', y el bot lo llevó a sesión de claridad. Es una sesión de inversión de fijo, no de claridad."*

### Por qué pasó
- El bot derivaba **demasiado rápido** sin suficiente contexto
- Tomaba la primera señal y decidía
- Christian: *"Las conversaciones del bot no tienen nada que ver con el entrenamiento que estuve haciendo yo"*

### 3 razones por las que esto duele a CV Finanzas
1. **Sesión de claridad NO se cobra** → afecta comisiones del equipo
2. Carlos prioriza inversión sobre claridad → si está saturado, una claridad mal-derivada se pospone (pierden el lead)
3. Sesión de claridad tiene **preguntas distintas** a inversión → se pierde data pre-llamada

---

## Problema #3 — Bot daba "consejos" financieros

### Caso reportado por Carlos
> *"El bot dio un consejo blanco y negro. Por tema regulatorio, yo no doy consejos por chat."*

### Regla agregada
> *"Mira, pareciera que ahí va como el consejo, pareciera que podrías hacer eso o el otro. Como no tengo toda la información, sería irresponsable de mi parte darte un consejo tal."* → llevarlo a una pregunta.

---

## Problema #4 — Bot muy pregúntico/intimidatorio

> Carlos: *"Hola me llamo Carlos. Hola soy Andy. Andy, ¿cuánto ganás?"* — el bot iba al hueso.

### Christian recordó
> *"Hay que tener mucho cuidado, el público tico es delicado con temas de finanzas. Es tabú preguntar 'cuánto ganás'. Más bien: 'contás con ingresos fijos, actualmente cómo estás organizado con tus gastos'..."*

---

## Problema #5 — Seguimientos repetitivos

> Christian: *"El seguimiento sigue poniendo el mismo mensaje. Hasta recién lo borré."*

**Solución:** cada seguimiento debe ser DIFERENTE. Andres lo va a ajustar.

---

## Decisión estratégica de la reunión — RETROCEDER

### Propuesta de Javier Raaz (acordada)
> *"Vayamos por fases. Primero: que NO dé recomendaciones de absolutamente nada — sea literalmente un calificador. Si detecta que califica, que entre Christian y revise antes de enviar el calendar."*

### Decisión final
1. ✅ **Apagar bots de asesoría/revisión/claridad** (que no envíen Calendly directo)
2. ✅ **Mantener solo el orquestador** activo
3. ✅ **Que el orquestador levante la mano a Christian** después de hacer las preguntas
4. ✅ Christian valida si está bien derivado → recién ahí envía el Calendly manual

### Razón
> Andres: *"Pulamos bien el orquestador. Una vez que esté andando bien, ahí activamos los bots de cada destino que ya están listos para enviar Calendly."*

---

## Cómo se va a iterar el orquestador (acordado)

### Christian + Carlos
- Mandar capturas de conversaciones por WhatsApp
- Andres tiene un proyecto en Claude.ai donde pega los feedbacks
- Itera el prompt continuamente

### Reuniones más frecuentes
- Antes: 1/semana (lunes)
- Ahora: **2/semana** mientras se itera
- Lunes 6pm Costa Rica / 9pm Argentina

---

## Definiciones del filtro completo (Christian explicó en vivo)

### Filtro 1 — Pregunta clave
```
¿A vos qué te gustaría más?
- Rentabilizar tus ahorros
- Hacer una revisión de algún producto que ya hayas adquirido o estés evaluando
- O aprender a gestionar vos mismo tus finanzas
```

### Filtro 2 — Pregunta sutil
> *"Por cierto, ¿a qué te dedicás?"* (filtro económico indirecto)

### Filtro 3 — Si quiere aprender (para sesión de claridad)
> *"Contás con ingresos fijos? Cómo estás organizado con tus gastos, deudas, pagos?"*

---

## Casos extremos discutidos

### Caso "no tengo plata, vendo loterías"
- Christian: *"Había uno ayer que vendía loterías, ganaba dinero ínfimo. No podías hacer nada con esa persona"*
- **Decisión:** Esto va al **libro** — no a sesión de claridad
- Mensaje de descarte: *"Para que vos te organices con tus gastos y deudas, está bueno que leas el libro. Después entramos en una fase directa de cómo rentabilizar tu dinero"*

### Caso "rentabilizar pero poca plata"
- Carlos: *"El filtro real es el pago de USD 100"*
- Christian filtra antes con "¿a qué te dedicás?" — si vende lotería → libro

---

## Configuración de notificaciones a Christian

### Acordado
- Notificación al **WhatsApp** (cuando se conecte)
- App móvil de GHL → notificaciones push
- Mientras tanto: notificación por email + revisar conversaciones

---

## Speeches finales validados (de Christian)

### Speech asesoría $100
```
En el caso que me comentás, lo que haríamos sería una sesión de una hora por
videollamada que tiene un costo de USD 100 + IVA. Solo será un pago ÚNICO ya
que una vez que hayamos elegido el producto para poner a rentabilizar tus
ahorros, vamos a tener revisiones cada cierto tiempo y también vas a tener
acceso a mis consultas SIN COSTO.

Digamos que se crea una relación duradera por el tiempo que lleve las
acciones que vamos a tomar. ¿Qué te parece esta opción?
```

### Speech revisión $150
Misma estructura, cambiar:
- Monto a USD 150
- "elegido el producto para rentabilizar" → "revisado tu producto y analizado las mejores opciones"

---

## Insights estratégicos del Andres

> *"El concepto que les tengo es: yo lo voy a ajustar, les paso el prompt para que lo vean, e iteramos. Vamos a hacer esto 2 veces por semana porque es complejo su filtro, chicos."*

> *"Vamos a tener gente que va a alargar — los podemos perfilar hasta el final con el bot. Y va a haber gente que la vamos a tener que ir llevando de a poquito y nos va a tener que levantar la mano. La idea es acotar eso."*

---

## Pendientes al cierre

- [ ] Andres: pagar (apagar) los bots de asesoría/revisión/claridad temporal
- [ ] Andres: dejar SOLO el orquestador andando con levantar-la-mano
- [ ] Andres: mejorar el prompt del orquestador con TODO el contexto de esta reunión
- [ ] Christian: instalar app móvil GHL (Android)
- [ ] Christian: probar el orquestador en el grupo
- [ ] Carlos + Christian: mandar capturas con feedback continuo
