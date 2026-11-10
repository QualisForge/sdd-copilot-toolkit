# AGENTS — [NOMBRE_PROYECTO]

**Estado:** Pendiente de aprobación

## Contexto, alcance y fuentes de verdad
- Constitución: `docs/constitution.md`.
- Historia activa: `HU/[ID].md`.
- SPEC, PLAN y TASKS: `specs/[ID]-[slug]/`.
- Código, pruebas y README existentes.

## Reglas de preparación SDD
- **Documento distinto de Constitución:** esta plantilla crea instrucciones del repositorio, **no** los principios fundacionales. Mantener los principios en `docs/constitution.md` y referenciarlos aquí; solo crear este `AGENTS.md` después de la aprobación explícita de Constitución.
- **No saltar gates:** el agente preparador solo redacta el documento de la fase activa y se detiene a solicitar aprobación; no generar Constitución y AGENTS juntos. Si falta Constitución, preparar esa fase primero.
- Preguntar una duda a la vez; no inventar requisitos.
- **SPECIFY y CLARIFY son fases distintas:** no aprobar SPEC ni iniciar PLAN antes de registrar CLARIFY, aunque no haya preguntas.
- Distinguir decisiones funcionales de técnicas y exigir aprobación por artefacto.
- PLAN debe incluir pruebas automatizadas reproducibles y el comando previsto o excepción expresa; TASKS debe desglosar su preparación y ejecución.
- PLAN también define ambiente y pasos concretos para abrir la solución, que terminarán en README.
- Una decisión nueva en PLAN reabre la parte pertinente de SPEC con autorización.

## Reglas de implementación y control
- Una tarea autorizada por vez, sin adelantarse.
- Crear tests unitarios y/o funcionales automatizados **almacenados**, ejecutar el comando y verificar regresión. Las pruebas manuales complementan, no sustituyen.
- Informar casos PASARON/FALLARON/NO EJECUTADOS con comandos y evidencia, diff y riesgos.
- README debe explicar cómo arrancar y ver el producto, no solo su propósito, y actualizarse con cambios reales.
- Controlar grupos Git; solicitar autorización para commits, push, PR, merge, tags o eliminación de ramas.
- Evitar secretos y cambios no autorizados.

## Convenciones confirmadas del repositorio
- Tecnología: [CONFIRMADA_O_POR_DEFINIR_EN_PLAN].
- Pruebas, comandos y ubicaciones: [CONFIRMADOS_O_POR_DEFINIR_EN_PLAN].
- Reglas existentes de `.github/copilot-instructions.md`: [COMPATIBILIDAD].

## Aprobación de AGENTS
- **Aprobador:** [PENDIENTE / Usuario].
- **Fecha de aprobación:** [PENDIENTE / FECHA_FIABLE / No determinada].
- **Evidencia:** [PENDIENTE / Aprobación explícita del usuario en esta conversación].
> Al aprobarlo, cambiar la cabecera a «Estado: Aprobado», guardar y releer; no comenzar SPECIFY en la misma respuesta.
