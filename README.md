# Ecosistema de Automatización IA Autónomo para Negocios
### Triage inteligente de tickets de soporte con validación humana (HITL)

**Entrega Final — Curso Coder "IA Automation"** · Autor: Armando Ismael

---

## Qué resuelve
Un sistema autónomo que recibe tickets de soporte, los **clasifica y responde con IA**, y **espera la aprobación de un humano** antes de contactar al cliente.

## Stack (4 tecnologías integradas)
- **Orquestador:** Make (2 escenarios)
- **Base de datos / memoria:** Airtable (3 tablas vinculadas)
- **Procesamiento IA:** OpenAI GPT-4o-mini (salida JSON)
- **Canal de salida + validación humana:** Slack

## Arquitectura
**Flujo 1 — Generación + Pausa HITL:** Airtable (ticket "Pendiente") → OpenAI (clasifica + redacta) → Parse JSON → Airtable ("Esperando Aprobación") → Slack (aviso).
Ruta de error: si la IA falla, registra en **Errores_Log** y continúa con valor sustituto (Resume).

**Flujo 2 — Publicación Condicional:** Airtable (busca "Aprobado por Humano") → Compuerta HITL → Slack (respuesta al cliente) → Airtable ("Resuelto").

Ciclo de estados: `Pendiente → Esperando Aprobación → Aprobado por Humano → Resuelto` (fallos → `Errores_Log`).

## Dashboard ejecutivo (en vivo, solo lectura)
https://airtable.com/appLG6Za2wB2QI5vk/shre1SyRPn6WzSsRX

## Contenido del repositorio
- `Documentacion_Tecnica.pdf` — arquitectura, estructuras de datos, estrategia de modelos y seguridad/resiliencia (Criterios 1-4).
- `blueprints/` — los 2 flujos de Make en `.json`.
- `capturas/` — evidencias del sistema funcionando.
- `video/` — demo de 3 minutos (o link en este README).

## Cobertura de la rúbrica
| Criterio | Dónde |
|---|---|
| 1 · Arquitectura | PDF (diagramas) |
| 2 · Estructuras de datos + JSON | PDF |
| 3 · Selección de modelos | PDF (cuadro comparativo) |
| 4 · Seguridad y resiliencia | PDF + captura Errores_Log |
| 5 · Dashboard | Link Airtable (arriba) |

## Nota de seguridad
Las credenciales (API keys, tokens) viven en las conexiones de Make, **no** en los blueprints ni en el repo. Flujos con variables dinámicas, sin datos hardcodeados.
