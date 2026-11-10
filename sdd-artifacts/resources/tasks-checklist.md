# Control TASKS: piezas verificables y grupos Git

## Criterios
- [ ] PLAN está **aprobado, incluida la propuesta tecnológica**; no escoger ni sustituir stack desde TASKS sin devolver el cambio a PLAN y solicitar nueva aprobación.
- [ ] Para cada tarea existe casilla `- [ ] T### ...` o estado equivalente legible, objetivo, dependencia y RF/CA asociado.
- [ ] Cada tarea tiene la línea exacta **«Hecho cuando:»** con una comprobación observable y tests que pueden correr al terminarla, sin adelantar otra tarea.
- [ ] **20–30 minutos es referencia** para una tarea común; tareas de 10–20 minutos están bien, 45–60 pueden justificarse; dividir cuando cambian responsabilidades o la verificación depende de código futuro.
- [ ] Ordenar ambiente/runner antes del código que lo necesite; mantener tests automatizados con la funcionalidad (preferir escribir casos antes cuando sea viable).
- [ ] Distinguir tests unitarios/funcionales, negativos y regresión; matriz RF/CA → tarea → prueba concreta con archivo/comando previsto.
- [ ] Incluir README desde el proyecto nuevo o actualización para nueva HU; no publicitar funciones no implementadas.
- [ ] Agrupar tareas en commits coherentes, con ID, integrantes, criterio de cierre y Conventional Commit sugerido. **No realizar commits sin autorización**.
- [ ] Dejar TASKS pendiente de revisión y no entrar a IMPLEMENT antes de aprobación.

## Si una tarea no supera su Quality Gate por dependencia futura
Reorganizar tareas o mover el test al momento adecuado; no aprobarla basándose en tests que todavía no pueden ejecutarse.
