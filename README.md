# Jerónimo Sánchez

Diseño y construyo sistemas que garantizan la calidad de agentes
conversacionales a lo largo de su ciclo de vida.

---

## Sistema de Automatización CD

| Repo | Qué hace | Estado |
|---|---|---|
| [ACT](https://github.com/jeronimosanchez/cx-automation-template) | Deploy idempotente de artefactos a Dialogflow CX — 12 recursos, CI/CD con WIF | ✅ Operativo |
| [QAP](https://github.com/jeronimosanchez/agent-validation-engine) | Validación: 51 TCs contra el agente real + cribador local $0 con LLMs | ✅ Operativo — en evolución |
| [GEN](https://github.com/jeronimosanchez/GEN) | Generación adversarial de artefactos conversacionales | 🔵 En construcción |
| [RES](https://github.com/jeronimosanchez/RES) | Investigación continua que alimenta la knowledge base | 🔵 En construcción |

---

## El caso de uso — Petal

Petal es un agente de floristería en Dialogflow CX construido como simulación
de producción real. Sus problemas de robustez iniciales se convirtieron en la
razón de construir el sistema CD: cada optimización pasa por el pipeline,
cerrando el ciclo. Petal y el sistema co-evolucionan.

---

## Qué resuelve

Iterar un agente conversacional es caro, desplegar es arriesgado, y medir
si algo mejoró es difícil. CD convierte ese ciclo en un pipeline reproducible:

- **Conocimiento acumulado** — el conocimiento de diseño conversacional se
  acumula en la organización en lugar de quedar disperso en personas.
- **Herramienta validada** — los equipos que construyen agentes conversacionales
  disponen de un pipeline probado desde el primer día.
- **Agnóstico de plataforma** — el conocimiento se organiza separando principios
  universales de diseño conversacional del conocimiento específico de plataforma,
  lo que permite su extensión natural a otras infraestructuras conversacionales.

---

## Capacidades del sistema

*El sistema está en construcción incremental. Las capacidades descritas
combinan funcionalidad operativa con líneas de desarrollo activas.*

**Control y gobernanza**
- Control total del sistema conversacional desde lenguaje natural — cualquier
  componente se despliega, prueba u optimiza sin tocar la plataforma directamente.
- El humano decide en los puntos que importan — la IA orquesta el ciclo;
  el humano aprueba lo que va a producción y elige qué fix se aplica.

**Análisis y validación**
- Diagnóstico preciso de causa raíz — identifica en qué capa falla el agente
  con evidencia trazable, no inferencias.
- Tres sistemas de control con distinto nivel de implementación — **hard eval**
  (operativo: validación determinista), **juez** (operativo: calidad
  conversacional con rúbricas), **adversarial** (en construcción: genera
  y enfrenta candidatos).
- Diagnóstico y solución forman un todo validado por dato real — detecta el
  fallo, genera candidatos de fix, despliega los mejores y contrasta su
  eficacia antes/después en producción. El mismo dato que detectó el problema
  confirma que está resuelto.

**Conocimiento y eficiencia**
- Conocimiento incremental en capas — enriquecido desde dos fuentes:
  investigación contrastada y experiencia empírica en proyectos reales.
  Reutilizable entre clientes.
- Diseñado para coste mínimo — automatización local y agentes en local
  filtran y criban a coste cero. Solo escala a cloud para validar
  los mejores candidatos.
