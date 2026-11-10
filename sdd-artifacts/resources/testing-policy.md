# Gate de pruebas automatizadas: requisitos mínimos

PLAN debe responder:
- ¿Qué se comprobará automáticamente? Relacionar requisitos/criterios con casos **positivos y negativos**.
- ¿Qué nivel? Unitario para lógica aislable; funcional/integración/UI si la interacción visible importa. Elegir al menos uno según riesgo y viabilidad.
- ¿Con qué herramientas y comando reproducible? Reutilizar lo existente; en nuevo proyecto proponer enfoque ligero y pedir acuerdo sobre dependencias de desarrollo.
- ¿Dónde vivirán los tests y qué datos/fixtures necesitan? Nombres y ubicación por definir en PLAN; concretar en TASKS.
- ¿Cómo ejecutar en Mac y Windows? Preferir un comando de proyecto compatible; explicar variantes cuando hagan falta.
- ¿Qué regresión aplica y qué evidencia guarda el informe?

**NO** equivale a una suite: una comprobación manual de botones, una sesión de navegador headless que el agente ejecutó sin guardar el caso, ni `node --check` solo (sintaxis, no comportamiento). Pueden ser controles útiles adicionales, pero **no** sustituyen los tests que otro usuario puede volver a ejecutar.

Si no existe runner, PLAN y TASKS deben contemplar configuración antes de implementar lo que se prueba. Si automatización es inviable, documentar limitación + riesgos + propuesta de validación alternativa y solicitar **excepción expresa** antes del gate; no decidir por el usuario.

En IMPLEMENT: escribir tests con la funcionalidad, ejecutar los comandos, conservar salida, separar PASÓ / FALLÓ / NO SE EJECUTÓ. No inventar tests ni cifras.

**Validación final**: revisar cada RF y criterio aprobado, listar prueba automatizada y resultado real (PASÓ / FALLÓ / NO EJECUTADO) y emitir veredicto con defectos pendientes. Preferir escribir pruebas antes o junto a la funcionalidad cuando resulte práctico, sin imponer TDD de forma universal.
