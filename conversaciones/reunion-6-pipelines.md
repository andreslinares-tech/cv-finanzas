# Reunión 6 — Estructura de Pipelines CV Finanzas

Basado en pizarras dibujadas por Carlos durante la reunión del 2026-05-26.

---

## Pipeline 1 — Cliente Inversiones

| # | Etapa | Notas |
|---|---|---|
| 1 | Conversación mediante redes sociales | Entrada vía Christian + Bot |
| 2 | Reunión Asesoría Financiera (llamada) | Punto de decisión: ¿lo pierdo? ¿entra a follow ups? |
| 3 | Correo enviado | Propuesta + potencial para segunda llamada |
| 4.1 | Cliente envía información y agenda para datos finales | Camino directo a cierre |
| 4.2 | Cliente agenda segunda sesión | Cuando mantiene dudas |
| 5.1 | Cliente cerrado y ganado ✓ | Desde 4.1 |
| 5.2 | Cliente envía información para cerrar | Desde 4.2 (después de 2da sesión) |
| 6.2 | Cliente cerrado ✓ | Desde 5.2 |

### 4 posibles outcomes desde la etapa 2 (Reunión)
1. → 4.1 (cliente decidido, envía info)
2. → Follow ups (no responde / silencio)
3. → Perdido (dice no abiertamente)
4. → Mantiene dudas → 4.2 (segunda sesión)

### Tags de productos (potenciales y vendidos)
- Banca Privada
- Notas Estructuradas
- Dominion MSS
- ~~Seguros de Vida~~ (descartado)
- ~~Seguros Gastos Médicos~~ (descartado)

> Convención: tag por producto con sufijo `A` (abierto/potencial) o `C` (cerrado/vendido). Ej: `banca-privada-A`, `banca-privada-C`.

### Qué necesita Carlos
1. **Flujo** armado en pipeline
2. **Taggear productos potenciales** (cliente con $150k podría ir a banca privada, notas estructuradas, etc.)
3. **Taggear productos vendidos** (qué cerró efectivamente)
4. **Seguimiento a futuro** cada 6 meses con automatización de recordatorios — owner: **Emi**

---

## Pipeline 2 — Cliente Programa

| # | Etapa | Notas |
|---|---|---|
| 1 | Conversación mediante redes sociales | |
| 2 | Sesión de Claridad (gratuita, llamada) | Punto de decisión: ¿perdido? ¿follow ups? |
| 3 | Pago parcial o completo del programa ($1500) | → Cliente Cerrado |
| 4 | Correo de bienvenida y primeros pasos | Emi envía credenciales School |
| 5 | Módulo 1 | |
| 6 | Checkpoint 1 (15 min) | |
| 7 | Módulo 2 | |
| 8 | Checkpoint 2 | |
| 9 | Módulo 3 | |
| 10 | Checkpoint 3 | |
| 11 | Módulo 4 | |
| 12 | Checkpoint 4 | |
| 13 | Módulo 5 | |
| 14 | Checkpoint 5 | |
| 15 | Módulo 6 | |

> Los checkpoints son reuniones de 15 min cada 15 días. Cronología flexible — las semanas no siempre se cumplen. Carlos quiere poder mover manualmente al cliente entre módulos para no perder en qué punto está cada uno.

### Bifurcación final — cliente del programa que termina invirtiendo

```
Módulo 6 → ¿Cliente invierte al final del programa?
              ↓
           6.1 Cliente de Inversión o Seguro
              ↓
        Tag de origen: "vino-de-programa"
              +
        Tag de destino: Inversión / Seguros (con tipo)
              ↓
        Se mueve al Pipeline 1 (Cliente Inversiones) en etapa Cerrado/Ganado
        sin atravesar todas las etapas previas (ya es cliente cerrado)
```

Configuración técnica: usar la **secuencia** de GHL para mover automáticamente entre pipelines sin duplicar contacto (Andrés lo dejó configurado para no duplicar).

---

## Decisiones técnicas adicionales de la reunión

- **Calendarios**: migrar de Calendly a los calendarios de Sharp/GHL ya creados (Sesión de Claridad, Revisión de Productos, Asesoría Financiera). Cristian debe enviar esos links de ahora en adelante.
- **WhatsApp**: por ahora no conectar el proveedor ($39/mes). Follow ups via correo + notificación en app móvil GHL. Cuando se conecte, se usa número empresarial CVF (no el de Emi).
- **Correos**: Carlos los seguirá enviando desde Outlook (no desde GHL) para no perder el histórico si algún día deja la herramienta.
- **Campos personalizados nuevos**: crear carpeta `Pareja` con campos `correo_pareja` y `teléfono_pareja` para las cuentas conjuntas (Andrés ya los dejó creados en la reunión).
- **Import CSV de clientes existentes**: Emi descarga CSV, Andrés lo carga. Casos con múltiples productos por contacto (ej: Sebastián con aporte único + aporte mensual) → un solo contacto con tags múltiples.
