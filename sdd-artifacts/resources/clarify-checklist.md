# Gate CLARIFY: obligatorio entre SPECIFY y PLAN

1. Releer `HU/[ID].md`, borrador `spec.md`, constitución y documentación relacionada.
1a. Realizar **auditoría QA solo para detectar**: por RF registrar hallazgos, contradicciones, decisiones no descritas, estados/errores/límites y conflictos con reglas del producto. No asumir soluciones.
1b. Presentar hallazgos antes de resolver; preguntar **uno por turno** solo cuando una decisión sea necesaria. Registrar respuesta y diferencia concreta frente al borrador.
2. Inspeccionar cada requisito: disparadores, datos válidos/invalidos, vacío/nulo, límites, errores, estados y transiciones, resultados visibles, interacción con funcionalidades existentes, persistencia, privacidad/seguridad cuando corresponda.
3. Para cada vacío con impacto, **preguntar de una en una** sin asumir solución.
4. Actualizar la **misma** SPEC, requisitos, aceptación y casos límite con decisiones explícitas.
5. Registrar en `spec.md`: «CLARIFY ejecutado», fecha/identificador si procede, temas revisados, preguntas-respuestas y **pendientes**. Si no hay preguntas, escribir «Sin dudas relevantes pendientes» y enumerar comprobaciones.
6. Presentar resumen del cambio y pedir **aprobación explícita de SPEC**. No generar PLAN si falta esta constancia.
