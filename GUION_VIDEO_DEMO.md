# GUION DEL VIDEO DEMO (≈3 minutos)
### Entrega Final — Ecosistema de Automatización IA

> **⚠️ ANTES DE GRABAR:** cerrá cualquier módulo de Make que muestre la **API Key de OpenAI** o tokens. Nunca dejes credenciales a la vista. Grabá pantalla con OBS, la grabadora de Windows (Win+G) o Loom.

---

## Estructura (con tiempos aprox.)

### 0:00 – 0:20 · Presentación
> "Hola, soy Ismael. Este es mi proyecto final: un ecosistema de automatización con IA para el triage de tickets de soporte. Integra Make, Airtable, OpenAI y Slack, con una validación humana antes de responder al cliente."

### 0:20 – 0:50 · El Cerebro (Airtable)
- Mostrá la tabla **Tickets**: señalá los campos **Estado, Categoria, Urgencia, Sentimiento, Respuesta_Sugerida**.
- Mencioná las 3 tablas (Tickets, Agentes, Errores_Log) y el ciclo de estados: *Pendiente → Esperando Aprobación → Aprobado por Humano → Resuelto*.

### 0:50 – 1:40 · El Corazón (Make) — el disparo automático
- Abrí el escenario **"Final - Triage IA"**. Mostrá los 5 módulos y **la rama gris del Error Handler**.
- Creá un ticket nuevo en Airtable (Asunto + Cuerpo, Estado = Pendiente).
- Volvé a Make y tocá **"Run once"**. Mostrá los módulos poniéndose verdes.
- Mostrá en Airtable cómo la IA completó Categoría/Urgencia/Sentimiento/Respuesta y el estado pasó a **"Esperando Aprobación"**.

### 1:40 – 2:15 · El punto humano (HITL)
- Mostrá el mensaje que llegó a **Slack #revision-contenido** ("requiere aprobación").
- En Airtable, cambiá el Estado del ticket a **"Aprobado por Humano"**.
- Corré el escenario **"Final - Publicacion HITL"** → mostrá el aviso **"✅ Ticket RESUELTO"** en Slack y el ticket en **"Resuelto"**.

### 2:15 – 2:45 · Resiliencia (rutas de error)
- Mostrá la tabla **Errores_Log** con la fila de error registrada.
- Explicá: "Si la IA falla, el sistema no se rompe: registra el error acá y sigue funcionando."

### 2:45 – 3:00 · Cierre (Dashboard)
- Abrí el **dashboard público** (el link de Airtable) y mostrá los KPIs.
- Cerrá: "El sistema funciona de punta a punta, con manejo de errores y validación humana. Gracias."

---

## Checklist antes de subir el video
- [ ] No se ven API keys ni tokens en ningún frame.
- [ ] Se ve el trigger, el procesamiento de la IA y el resultado final.
- [ ] Dura ~3 minutos.
- [ ] Subilo (YouTube "no listado", Drive, o directo al repo) y pegá el link en el README.
