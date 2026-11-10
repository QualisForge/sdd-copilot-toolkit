# Control PLAN: decisiones técnicas, opciones y trazabilidad

## Si la historia no indica tecnologías
1. Confirmar qué está **aprobado** en constitución, AGENTS, SPEC y repositorio; para proyectos existentes, **reutilizar stack y componentes** como primera opción.
2. Si no hay stack, proponer durante **PLAN** una solución concreta y sencilla, considerando solo elementos aplicables: tipo de aplicación, lenguaje, framework o ausencia de él, almacenamiento, ejecución/despliegue y herramienta de tests.
3. Comparar con otra alternativa **solo cuando aporte valor**: adecuación a los RF, complejidad, dependencias y costo, mantenimiento, conocimientos confirmados, compatibilidad, seguridad y facilidad para probar y ejecutar. Registrar recomendación, ventajas, límites y razones para descartar la alternativa.
4. Marcar explícitamente **confirmado / propuesto para aprobación / por verificar**. No presentar sugerencias como acuerdos, ni inventar versiones, costos o comandos probados.
5. Mostrar la propuesta antes del cierre de PLAN. **Sin aprobación explícita del stack y PLAN, no crear TASKS**. Si se rechaza la propuesta, ajustar PLAN sin código.
6. Si una cuestión afecta el **QUÉ** (por ejemplo, aplicación web o sin conexión, datos guardados o no), regresarla a CLARIFY/SPEC con permiso. Si afecta solo el **CÓMO**, resolverla aquí.

## Revisión obligatoria
- [ ] Leer SPEC **aprobada después de CLARIFY**, constitución, AGENTS y código/pruebas vigentes.
- [ ] Describir componentes o módulos a crear, modificar o reutilizar, y qué RF cubre cada uno.
- [ ] Incluir flujos, entradas/salidas, errores, contratos y **modelo de datos solo si resulta relevante**; si no aplica, declararlo sin inventar tablas o entidades.
- [ ] Documentar **propuesta de stack** o reutilización del existente; para decisiones técnicas con impacto real, registrar elección, motivo, alternativa razonable considerada y por qué se descarta. No crear alternativas artificiales para detalles triviales.
- [ ] Matriz mínima RF/CA → componente → nivel/caso de prueba previsto. Identificar huecos de cobertura.
- [ ] Entorno reproducible: herramientas, dependencias, preparación, arranque, prueba y archivos ignorados; diferencias Mac/Windows solo cuando existan.
- [ ] Pruebas automatizadas repetibles: runner, archivos, datos y comando; incluir negativos/regresión. Si son inviables, documentar riesgo y excepción humana.
- [ ] README: creación/actualización y pasos de puesta en marcha **observables y verificables**, coherentes con el stack seleccionado.
- [ ] Aprobación explícita de la propuesta tecnológica y del PLAN antes de TASKS. No confundir recomendación con decisión definitiva.

## Detener ante una nueva regla funcional
No convertir una preferencia de implementación en requisito de negocio. Señalar el punto, solicitar aclaración y **proponer diff SPEC**; actualizar solamente tras aprobación, revisar trazabilidad y reaprobar PLAN antes de TASKS.
