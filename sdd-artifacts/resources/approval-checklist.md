# Control de aprobación: registrar y verificar cada Quality Gate

## Cuándo se considera aprobado
- El usuario revisó **una versión identificable** del artefacto de la fase activa y expresó su aprobación inequívoca, por ejemplo: «Aprobada la Constitución», «Apruebo AGENTS», «Apruebo SPEC», «Apruebo PLAN» o «Apruebo TASKS». No exigir una frase exacta si el documento está claro por contexto.
- «Iniciar SDD», «continúa» o «haz todo» no aprueban futuros documentos. Si hay duda sobre qué archivo se aprueba, preguntar **una sola cosa** antes de editar.
- Para SPEC, verificar además CLARIFY realizado; para PLAN, decisión tecnológica y pruebas planificadas. Si hay problemas críticos no resueltos, explicar y pedir corregir antes de dar el gate por cerrado.

## Protocolo obligatorio para project-initializer
1. Reconocer la aprobación del documento **ya presentado** y de su versión, sin inferir aprobación de otros artefactos.
2. **Editar inmediatamente el archivo de esa misma fase**, y solo sus metadatos: `**Estado:** Aprobada` (Constitución/SPEC) o `**Estado:** Aprobado` (AGENTS/PLAN/TASKS); `Aprobador: Usuario`; fecha **solo si es fiable** (si no, `No determinada`); y `Evidencia: aprobación explícita del usuario en esta conversación`. Sin cambios de contenido sustantivo.
3. **Releer el archivo del repositorio** y confirmar que estado, aprobador y evidencia persisten, sin estados inconsistentes ni contenido modificado. Si no puede verificarlo, informar el bloqueo y **no avanzar**.
4. Confirmar brevemente al usuario: archivo, estado registrado, fecha si disponible y próxima fase. **Detenerse**; en esa respuesta no crear el documento de la fase siguiente.
5. Solo en la interacción posterior y con gate verificado, iniciar la fase siguiente. Su borrador debe solicitar nueva aprobación.

## Casos especiales
- **Cambios solicitados:** mantener `Pendiente de aprobación` hasta presentar la nueva versión y obtener aprobación; nunca registrar aprobación anterior como válida para una revisión nueva.
- **Archivo antiguo marcado aprobado sin respaldo confiable:** preservar y solicitar confirmación o ratificación, no inventar evidencia histórica.
- **Metadatos duplicados:** sincronizar todos los campos de estado y aprobación; no dejar `Aprobado` y `Pendiente de aprobación` simultáneos. Preferir un único `Estado` visible en la cabecera.
- **Falla en edición/guardado:** no afirmar que está aprobado; intentar corregir solo esos metadatos o informar la limitación.
- **No modificar código, pruebas, README, AGENTS de una fase futura ni operar Git** mientras se registra una aprobación.

## Prueba de regresión obligatoria
Repositorio nuevo, solo `HU/HU-001.md`: iniciar SDD → preparar solo Constitución pendiente → usuario escribe «Aprobada la Constitución» → comprobar en disco `docs/constitution.md` con `Estado: Aprobada`, aprobador y evidencia → `AGENTS.md` aún no creado → siguiente interacción permite elaborar `AGENTS.md` como borrador pendiente. Repetir el control con AGENTS, SPEC, PLAN y TASKS.
