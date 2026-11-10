# Control de cambios: requisito nuevo o discrepancia SPEC–PLAN

## Orden obligatorio
1. Registrar nueva necesidad, fuente y artefactos relacionados.
2. Sin escribir código ni alterar documentos aprobados, identificar RF/CA afectado y analizar impacto en PLAN, TASKS, pruebas, README, regresión y compromisos previos.
3. Preguntar **una decisión por turno** cuando falte contexto; no asumir reglas.
4. Presentar **diff propuesto de `spec.md`** (o extracto antes/después) y solicitar autorización para modificarlo.
5. Con autorización, aplicar cambios mínimos, dejar nueva aprobación trazable y revalidar PLAN/TASKS y su Quality Gate; no ejecutar cambios funcionales ocultos.
6. Si cambia la arquitectura o las pruebas, actualizar también los documentos dependientes y solicitar sus aprobaciones antes de implementar.

## No permitido
- Tratar el comentario de Copilot como aprobación.
- Actualizar SPEC o código automáticamente solo porque se detectó el cambio.
- Omitir el impacto sobre comportamientos anteriores.
