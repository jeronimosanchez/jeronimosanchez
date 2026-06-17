# Jerónimo Sánchez

*Diseño y aseguramiento de calidad de agentes conversacionales*

Construyo el **método y la automatización** que llevan un agente conversacional por todo su ciclo
—diseñar, desplegar, validar y mejorar— con **criterio**, a **coste mínimo**, y haciendo que el
**conocimiento se acumule en la organización, no en las personas**.

---

## Qué resuelve

Iterar un agente conversacional es caro, desplegar es arriesgado, y medir la
mejora es difícil. CD **está diseñado para** convertir ese ciclo en un pipeline reproducible:

- **Conocimiento que se acumula y realimenta** — el conocimiento de diseño
  conversacional se acumula en la organización (no en personas) y **realimenta el
  propio sistema** en cada ciclo.
- **Herramienta reutilizable** — un pipeline diseñado para que los equipos lo
  reutilicen entre proyectos, en lugar de reinventarlo cada vez.
- **Vocación agnóstica** — separa los principios universales de diseño
  conversacional del conocimiento específico de plataforma, **diseñado para
  extenderse** a otras infraestructuras (objetivo aún por demostrar).

---

## Sistema de Automatización CD

| Repo | Qué hace | Estado |
|---|---|---|
| [ACT](https://github.com/jeronimosanchez/cx-automation-template) | Deploy idempotente de artefactos a Dialogflow CX — 12 recursos, CI/CD con WIF | ✅ Operativo |
| [QAP](https://github.com/jeronimosanchez/agent-validation-engine) | Validación: 51 TCs contra el agente real + cribador local $0 con LLMs (en calibración) | ✅ Operativo — en evolución |
| [GEN](https://github.com/jeronimosanchez/GEN) | Generación adversarial de artefactos conversacionales | 🔵 En construcción |
| [RES](https://github.com/jeronimosanchez/RES) | Investigación continua que alimenta la knowledge base | 🔵 En construcción |

Las 4 líneas las coordina **CD**, el hub de conocimiento y método (KB + metodología). Mapa completo, recorridos y estado de cada pieza en **[SISTEMA.md](https://github.com/jeronimosanchez/CD/blob/main/SISTEMA.md)**.

---

## Capacidades del sistema

*El sistema está en construcción incremental. Las capacidades descritas
combinan funcionalidad operativa con líneas de desarrollo activas.*

**Control y gobernanza**
- Control del sistema conversacional desde lenguaje natural — cualquier
  componente se despliega y se prueba sin tocar la plataforma directamente.
- El humano decide en los puntos que importan — la IA orquesta el ciclo;
  el humano aprueba lo que va a producción y elige qué fix se aplica.

**Análisis y validación**
- Diagnóstico de causa raíz con evidencia trazable — localiza **dónde falla** el
  agente a partir del trace y los datos, distinguiendo lo **verificado** de lo
  **supuesto** (no inferencias a ciegas).
- Tres sistemas de control con distinto nivel de implementación — **hard eval**
  (operativo: validación determinista), **juez** (funciona, sin calibrar: calidad
  conversacional con rúbricas), **adversarial** (en construcción: genera
  y enfrenta candidatos).
- **Sistema A — diagnóstico y reparación en un ciclo guiado por dato** — el sistema
  **está diseñado para** detectar el fallo, generar y cribar candidatos de fix,
  desplegar el mejor y confirmar su eficacia contra la plataforma real. El mismo dato
  que detectó el problema confirma que está resuelto; el fix validado se destila como
  **receta reutilizable en el KB (Sistema B)**. *(Bucle completo en construcción.)*

**Conocimiento y eficiencia**
- Conocimiento incremental en capas — enriquecido desde dos fuentes:
  investigación contrastada y experiencia empírica en el proyecto piloto.
  Reutilizable entre clientes.
- **El embudo — coste mínimo por diseño** — un cribador local ($0) propone y
  filtra candidatos; la plataforma real solo confirma los finalistas. El cribador
  no necesita ser perfecto: le basta con **ordenar bien**.

---

## El caso de uso — Petal

Petal es un agente de floristería en Dialogflow CX construido como simulación
de producción real. Sus problemas de robustez iniciales se convirtieron en la
razón de construir el sistema CD: cada optimización pasa por el pipeline,
cerrando el ciclo. Petal y el sistema co-evolucionan.
