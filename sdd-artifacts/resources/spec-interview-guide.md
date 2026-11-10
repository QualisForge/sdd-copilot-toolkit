# Guía de entrevista SPECIFY y criterios verificables

## Propósito
Comprender la historia sin imponer decisiones técnicas y redactar requisitos observables. **No sustituye** CLARIFY posterior.

## Orden sugerido (ajustable)
1. Leer historia `HU/[ID].md`, constitución, instrucciones y comportamiento previo disponible.
2. Identificar lo ya definido; no volver a preguntarlo.
3. Preguntar **una sola cuestión por turno** sobre: usuarios y objetivo; datos y reglas; estados/transiciones; errores y vacíos; casos límite; exclusiones y compatibilidad.
4. Como referencia, comenzar con **hasta 4–6 preguntas**, sin mínimo ni máximo estricto. Si persiste una ambigüedad que cambia resultados o pruebas, seguir preguntando; si no existe, no forzar preguntas.
5. Para cada respuesta, registrar decisión, requisito afectado y aspectos aún «Por definir». No inferir aceptación.
6. Redactar `spec.md` con RF numerados `[ID_HISTORIA]-RF-###`, **criterios EARS cuando corresponda** y casos positivos, negativos y límites. EARS de ejemplo: «Cuando [evento], el sistema deberá [comportamiento observable]»; «Si [fallo], el sistema deberá [respuesta verificable]».
7. Describir QUÉ y POR QUÉ, no decisiones de infraestructura o código. «Hecho/terminado» significa comprobación funcional, no reemplaza los Quality Gates de cada tarea.
8. Dejar la SPEC en borrador y pasar a una **auditoría CLARIFY diferenciada** antes de solicitar aprobación.

## Quality Gate de SPECIFY
- [ ] No hay supuestos convertidos en requisitos confirmados.
- [ ] RF y criterios verificables identificados; exclusiones y errores visibles.
- [ ] La entrevista es breve y suficiente para el contexto, no una batería mecánica.
- [ ] No se ha confundido SPECIFY con CLARIFY.
