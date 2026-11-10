# Tareas — [ID_HISTORIA] [TÍTULO]

**Estado:** Pendiente de aprobación
**Fuentes:** [RUTA_SPEC] / [RUTA_PLAN]
**Tecnologías y estrategia de pruebas aprobadas en PLAN:** [RESUMEN_DE_LA_DECISIÓN_Y_ESTADO_APROBADO; SI_FALTA_DETENERSE]
**Regla:** cada tarea debe poder verificarse al completarla, sin depender de funcionalidades futuras.
**Tamaño orientativo:** 20–30 min por tarea; 10–20 si es simple, hasta 45–60 si se justifica. Dividir por independencia y verificabilidad, no por cronómetro.

- [ ] **T001 — [PREPARAR_ENTORNO_Y_RUNNER_SI_APLICA]**
## T001 — [PREPARAR_ENTORNO_Y_RUNNER_SI_APLICA]
- **Estado:** Pendiente.
- **Alcance:** [INSTALAR_CONFIGURAR_REUTILIZAR_LO_APROBADO_EN_PLAN].
- **Depende de:** [NINGUNA_O_TAREA_PREVIA].
- **Tiempo orientativo:** [MINUTOS_Y_JUSTIFICACION_SI_EXCEDE_RANGO].
- **Cubre:** ambiente y base automatizada del PLAN.
- **Pruebas/Quality Gate:** [COMANDO_EJECUTABLE / TEST_DE_HUMO / EVIDENCIA].
- **Hecho cuando:** [ENTORNO_Y_RUNNER_REPRODUCIBLES].

- [ ] **T002 — [FUNCIONALIDAD_ATÓMICA_Y_SUS_TESTS]**
## T002 — [FUNCIONALIDAD_ATÓMICA_Y_SUS_TESTS]
- **Estado:** Pendiente.
- **Alcance:** [CAMBIO_ACOTADO].
- **Depende de:** [T001_SI_APLICA].
- **Tiempo orientativo:** [MINUTOS; NO_ES_LIMITE_RIGIDO].
- **Preferencia de verificación:** escribir casos automatizados antes de o junto al cambio cuando sea viable; no imponer TDD si no está aprobado.
- **Cubre:** [RF/CA].
- **Tests automatizados guardados:** [RUTA_TESTS], casos positivo y negativo realizables al finalizar T002.
- **Comando:** [COMANDO_PRUEBAS].
- **Hecho cuando:** [ASSERTS_PASAN_Y_GIT_DIFF_REVISION].

- [ ] **T003 — [SIGUIENTE_TRABAJO_PEQUEÑO]**
## T003 — [SIGUIENTE_TRABAJO_PEQUEÑO]
[REPETIR_ESTRUCTURA; DIVIDIR_CAMBIOS_COMPLEJOS_EN_TAREAS_PROPIAS]

- [ ] **T00N — [CREAR_O_ACTUALIZAR_README]**
## T00N — [CREAR_O_ACTUALIZAR_README]
- **Depende de:** [SOLUCION_Y_COMANDOS_EJECUTABLES].
- **Alcance:** documentar pasos Mac/Windows cuando difieran, abrir la aplicación, URL/pantalla, uso, detener servidor si aplica, ejecución y resultado esperado de pruebas.
- **Hecho cuando:** otra persona puede seguir las instrucciones confirmadas o se indican claramente partes por validar.

- [ ] **T00X — [REGRESIÓN_Y_CIERRE]**
## T00X — [REGRESIÓN_Y_CIERRE]
- **Alcance:** ejecutar suite, revisar cobertura, comprobar arranque e instrucciones README; no ampliar funcionalidad.
- **Hecho cuando:** tests y calidad pasan, con informe fiel de fallos/excepciones.

## Matriz de trazabilidad
| Requisito/criterio | Tarea | Test automatizado nombrado y archivo | Evidencia |
|---|---|---|---|
| [RF-001/CA-01] | [T002] | [TEST + RUTA] | [COMANDO/RESULTADO] |

## Grupos lógicos de commits
### G001 — [TEMA]
- **Tareas:** [LISTA_COERENTE].
- **Cierre:** tareas y tests/checks realizados, Quality Gates revisados.
- **Mensaje sugerido:** `feat(scope): describe change`.
- **Estado:** Abierto / Listo para permiso / Registrado.

## Aprobación
- **Aprobador:** [PENDIENTE / Usuario].
- **Fecha de aprobación:** [PENDIENTE / FECHA_FIABLE / No determinada].
- **Evidencia:** [PENDIENTE / Aprobación explícita del usuario en esta conversación].
> Tras aprobación expresa, cambiar **Estado de la cabecera** a «Aprobado», guardar y releer para verificar. El inicializador **no inicia IMPLEMENT**.
