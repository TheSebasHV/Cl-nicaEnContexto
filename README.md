# Clínica en Contexto

Recurso formativo para el abordaje psicológico en el cuidado crónico.

| Archivo | Qué es |
|---|---|
| `index.html` | Página principal: Inicio (Biblioteca Relacional), Fundamentos, Casos Clínicos y **Foro**. |
| `config.js` | Configuración del foro (Supabase). Es el único archivo que hay que editar para el foro. |

Ambos archivos deben publicarse juntos, en la misma carpeta.

## Foro de experiencias hospitalarias

El foro es la cuarta pestaña. Es anónimo: cada visitante recibe una sesión anónima de Supabase al abrir la pestaña (no antes).

**Configuración** (`config.js`): `SUPABASE_URL`, `SUPABASE_KEY` (solo la clave *anon* / *publishable*, **nunca** la `service_role` ni la *secret*) y `NOMBRE_FORO`.

**Requisitos en Supabase** (ya configurados en el proyecto actual):
- *Authentication → Sign In / Providers → Allow anonymous sign-ins* activado.
- Tablas `mensajes` y `votos` con sus políticas y reglas: respuestas de un solo nivel, un voto por mensaje, no votar como útil un mensaje propio, voto negativo con motivo obligatorio, y ocultamiento automático con 2 votos negativos. Los mensajes no se pueden editar ni borrar desde la página.

**Moderación**: los mensajes ocultados por la comunidad se revisan desde el panel de Supabase (*Table Editor → mensajes*), donde se eliminan o se restauran.
