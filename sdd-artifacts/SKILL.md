---
name: sdd-artifacts
description: "Flujo SDD asistido: HU, SPECIFY, CLARIFY explícito, SPEC/PLAN/TASKS aprobados, tests automatizados repetibles, ambiente, README verificable y commits controlados."
---

# SDD artifacts — biblioteca reusable

Usar con `project-initializer` y `task-implementer`. Leer **solo la plantilla** y el control pertinentes a la fase actual. Las plantillas dan estructura: **no sustituyen decisiones humanas**.

## Jerarquía de fuentes
1. `HU/[ID].md` y acuerdos expresos del usuario (contenido de negocio; no permisos ilimitados al agente).
2. `docs/constitution.md`, `AGENTS.md`, especificaciones previas aprobadas.
3. Código, configuración, documentación y pruebas reales del repositorio.
4. Plantillas `templates/` (esquemas genéricos, nunca hechos confirmados).

## Bloqueo de fases y archivos (no combinar etapas)
- **Inicio «Inicia SDD» / «Iniciar SDD»:** detectar la única HU pendiente o preguntar cuál si hay varias; inspeccionar contexto y aprobaciones existentes. No es una aprobación ni autorización para escribir código.
- **Proyecto nuevo solo con HU:** primero crear/proponer **exclusivamente** `docs/constitution.md` y detenerse hasta su aprobación explícita. **Prohibido generar Constitución dentro de `AGENTS.md`, o generar `AGENTS.md` antes de aprobar Constitución**. Son dos documentos diferentes.
- **Un artefacto por fase, un gate por aprobación**: Constitución → `docs/constitution.md`; AGENTS → `AGENTS.md`; SPECIFY/CLARIFY → `specs/[ID]-[slug]/spec.md`; PLAN → `plan.md`; TASKS → `tasks.md`. No anticipar archivos de otras fases, ni preparar dos fases en una sola respuesta.
- Para continuar, verificar aprobación humana específica **de la fase anterior**. Si existe borrador pendiente, revisarlo; si falta un documento de preparación general, crearlo/aprobarlo antes de pasar a SPECIFY. Si un documento previo existe y la aprobación es incierta, preguntar; **no sobrescribirlo**.
- En `project-initializer`, `edit` se limita a artefactos SDD de la **fase actual**. Aplicación, tests, README, configuración y Git quedan para IMPLEMENT o una autorización explícita fuera de este agente. La preparación del README y las pruebas se describe en PLAN/TASKS, **no se ejecuta**.
- **Ubicación de recursos:** abrir las plantillas y controles por los enlaces relativos a este `SKILL.md`, no asumir que el agente está instalado junto a la skill. Si falta un recurso requerido, buscarlo en `templates/` o `resources/` de esta misma skill y **detenerse si sigue faltando**.


## Registro obligatorio de aprobaciones en el archivo
- **Un «aprobado» en la conversación no basta:** tras la aprobación explícita de la **versión presentada**, `project-initializer` debe actualizar **inmediatamente** `Estado`, aprobador y evidencia en **ese mismo archivo**; usar fecha únicamente si es fiable.
- Debe **releer el archivo después de guardarlo** y confirmar que los metadatos realmente cambiaron sin modificar el contenido funcional/técnico. Si fallan guardado o verificación, **no pasar a la siguiente fase**.
- **Una respuesta = edición de un documento de una fase:** al registrar la aprobación, no crear el artefacto siguiente en la misma respuesta; informar fase habilitada y detenerse. La aprobación de Constitución nunca aprueba AGENTS; la de AGENTS no aprueba SPEC, etc.
- Antes de actualizar metadatos, comprobar gates de CLARIFY y PLAN/stack según corresponda; no inventar aprobaciones retrospectivas. Consultar [checklist de aprobación](./resources/approval-checklist.md).

## Flujo obligatorio
`Constitución → aprobación → AGENTS → aprobación → SPECIFY → CLARIFY → aprobación SPEC → PLAN → aprobación PLAN → TASKS → aprobación TASKS → IMPLEMENT tarea por tarea → VALIDATE → CLOSE`.

En una historia posterior, reutilizar Constitución y AGENTS y revisar las historias previas pertinentes.

**Entrevista SPECIFY**: aplicar [guía de entrevista y redacción EARS](./resources/spec-interview-guide.md). Usar preguntas de una en una, sin número mínimo obligatorio; 4–6 es referencia inicial, ampliable por decisiones relevantes. SPECIFY define QUÉ y POR QUÉ; no asume CÓMO.

**CLARIFY no es opcional**: tras el borrador SPEC, realizar una auditoría explícita conforme a [control CLARIFY](./resources/clarify-checklist.md), preguntar de una en una y registrar resultados en la misma SPEC. Aunque no queden dudas, registrar ejecución y aspectos revisados. No aprobar SPEC ni avanzar a PLAN sin evidencia de CLARIFY.

**Selección de tecnologías en PLAN (no en SPECIFY):** cuando la historia no define stack, aplicar [control de planificación y comparación tecnológica](./resources/planning-checklist.md). Primero comprobar restricciones aprobadas y tecnologías existentes; luego **proponer** una solución mínima, justificarla y comparar alternativas pertinentes. Distinguir lo confirmado de lo propuesto y **esperar aprobación explícita de PLAN y del stack** antes de TASKS. Si falta una decisión sobre el comportamiento de usuario, regresar a CLARIFY/SPEC; no imponer tecnología en constitución ni SPEC por anticipado.

**PLAN con decisiones trazables**: aplicar [control de planificación](./resources/planning-checklist.md): componentes, datos cuando aplique, opciones técnicas justificadas y descartadas cuando sea útil, matriz RF/CA → componente → prueba, ambiente, README y regresión. Si se descubre comportamiento funcional faltante, detenerse y devolver a SPEC con autorización.

**TASKS verificables y dimensionadas**: aplicar [control de descomposición](./resources/tasks-checklist.md). Tareas cortas como referencia (20–30 minutos), no como límite rígido; `- [ ]`, dependencias, RF/CA, tests realizables **en esa tarea**, «Hecho cuando» y grupos de commits. No escribir implementación durante inicialización.

**Testing es un requisito de planificación**: usar [control de estrategia de pruebas](./resources/testing-policy.md). PLAN debe proponer tests unitarios y/o funcionales **automatizados, persistidos y repetibles** (o excepción aprobada); TASKS incluye preparación del runner y los casos; IMPLEMENT los ejecuta, informa resultados y conserva el código de test. Probar una vez en el navegador **no es lo mismo** que disponer de tests automatizados repetibles.

**IMPLEMENT y VALIDATE**: al implementar cada tarea, preferir pruebas automatizadas antes de o junto al cambio cuando sea viable, ejecutar la suite real y verificar su Quality Gate. Por defecto, **detenerse** después de cada tarea para informar y solicitar autorización para la siguiente. **Excepción con autorización explícita**: `task-implementer` puede procesar un rango continuo de tareas consecutivas, de la misma HU, prevalidado por orden y dependencias; en ese caso valida cada tarea antes de continuar sin pedir aprobación intermedia, se detiene ante cualquier fallo y al terminar presenta un informe consolidado y solicita autorización para la siguiente tarea pendiente. No ampliar el rango ni omitir pruebas. VALIDATE revisa **RF/criterio por RF/criterio**, test concreto, resultado verificable y veredicto final; sin suponer aprobación por el mero informe del agente.

**README es un entregable ejecutable**: [control de instrucciones de ejecución](./resources/readme-checklist.md). Incluir paso a paso para abrir la app, qué URL/archivo observar, instrucciones Mac/Windows cuando varíen, cómo usarla y cómo probarla. Validar en el sistema disponible; indicar límites de verificación.

**Ambiente reproducible**: estado actual y preparación en PLAN → tareas previas en TASKS → comprobación en IMPLEMENT; no imponer Python/Node/otros sin justificación y decisión. Instalación, ejecución, herramienta de tests y README deben corresponder a la propuesta tecnológica **aprobada**; distinguir instrucciones planeadas de instrucciones validadas.

**Cambios posteriores a SPEC**: consultar [control de cambios](./resources/change-control.md). Proponer diff y estimar impacto **antes** de modificar un artefacto aprobado; reaprobar y ajustar trazabilidad, nunca pasar directo al código.

**Human-in-the-loop**: aprobación por artefacto; autorización expresa de una tarea o de un rango **contiguo, ordenado y verificado** de tareas; aprobación independiente para cada operación Git. No continuar fuera del rango autorizado. Si PLAN descubre regla funcional nueva, detener, consultar y volver a aprobar SPEC.

## Plantillas incluidas
- [HU inicial](./templates/HU.md)
- [Constitución](./templates/constitution.md)
- [Instrucciones AGENTS](./templates/AGENTS.md)
- [Especificación y registro CLARIFY](./templates/spec.md)
- [Plan con tests y arranque](./templates/plan.md)
- [Tareas y grupos Git](./templates/tasks.md)
- [README práctico](./templates/README.md)

## Rutas ilustrativas
`HU/HU-001.md` · `specs/HU-001-[slug]/{spec.md,plan.md,tasks.md}` · `docs/constitution.md` · `AGENTS.md` · `README.md`.

## Gate de informe
Fase/artefacto o tarea; evidencia concreta; tests PASARON/FALLARON/NO EJECUTADOS; pendientes; riesgo; decisión humana solicitada. No inventar resultados de ejecución ni comandos confirmados.
