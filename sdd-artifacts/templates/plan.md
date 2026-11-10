# Plan técnico — [ID_HISTORIA] [TÍTULO]

**Estado:** Pendiente de aprobación (incluida la decisión tecnológica)
**SPEC base aprobada + CLARIFY cerrado:** [RUTA_SPEC] / [COMPROBACIÓN]

## Contexto tecnológico: lo que ya está definido
- **¿La HU indica tecnología?** [SÍ/NO; CITAR FUENTE O INDICAR NO DEFINE].
- **Restricciones aprobadas (constitución/AGENTS/SPEC):** [RESTRICCIONES_REALES_O_NINGUNA].
- **Tecnología existente que se puede reutilizar:** [STACK_VERIFICADO_EN_REPO_O_PROYECTO_NUEVO].
- **Estado de la decisión:** [PROPUESTA_PENDIENTE_DE_APROBACIÓN / REUTILIZACIÓN_PARA_APROBAR / APROBADA_CON_FECHA].

## Propuesta tecnológica — decisión de PLAN
> Si no existe stack definido, **proponer aquí**, no imponerlo desde SPECIFY/CLARIFY. Escribir en lenguaje sencillo y no introducir herramientas innecesarias.

| Elemento | Recomendación concreta o «No aplica» | Por qué conviene al caso | Estado (confirmado/propuesto/por verificar) |
|---|---|---|---|
| Tipo de solución / plataforma | [WEB_ESCRITORIO_CLI_OTRA] | [MOTIVO] | [ESTADO] |
| Lenguaje / framework (o sin framework) | [OPCIÓN] | [MOTIVO] | [ESTADO] |
| Persistencia / datos (si aplica) | [OPCIÓN_O_NO_APLICA] | [MOTIVO] | [ESTADO] |
| Ejecución y entrega / despliegue | [OPCIÓN_O_NO_APLICA] | [MOTIVO] | [ESTADO] |
| Herramientas para pruebas | [RUNNER_Y_NIVEL] | [MOTIVO] | [ESTADO] |

### Alternativas y criterio de elección
| Opción | Ventajas | Limitaciones, dependencias o costos | Recomendación |
|---|---|---|---|
| [RECOMENDADA_O_REUTILIZADA] | [BENEFICIOS] | [COMPROMISOS] | [POR_QUÉ] |
| [ALTERNATIVA_SI_APORTA_VALOR] | [BENEFICIOS] | [COMPROMISOS] | [POR_QUÉ_NO] |

- **Factores revisados:** simplicidad, encaje con RF, mantenimiento, compatibilidad, seguridad, pruebas, preparación y costo cuando sea relevante.
- **Decisión solicitada al usuario:** [APROBAR_PROPUESTA / ELEGIR_ALTERNATIVA / ACLARAR_RESTRICCIÓN].
- **Condición de avance:** no pasar a TASKS hasta que el usuario apruebe expresamente la propuesta tecnológica como parte de PLAN. Si hay una duda funcional, volver a CLARIFY/SPEC.

## Diseño y componentes
[COMO_IMPLEMENTAR_SIN_CAMBIOS_INNECESARIOS]
| Componente | Acción (crear/reutilizar/modificar) | Por qué |
|---|---|---|
| [ARCHIVO] | [ACCIÓN] | [JUSTIFICACIÓN] |

## Flujos, errores y datos
[ENTRADAS_PROCESOS_SALIDAS_ERRORES_CONTRATOS]
- **Modelo de datos (si aplica):** [ENTIDADES_ATRIBUTOS_RELACIONES_O_NO_APLICA; NO_INVENTAR_TABLAS].

## Decisiones técnicas y alternativas relevantes
| Decisión | Opción elegida y motivo | Alternativa considerada | Razón para no elegirla | RF/CA afectado |
|---|---|---|---|---|
| [DECISIÓN_RELEVANTE] | [ELECCION_JUSTIFICADA] | [ALTERNATIVA_REAL_O_NO_APLICA] | [MOTIVO_O_NO_APLICA] | [RF/CA] |

> No fabricar alternativas para decisiones triviales. Si una opción cambia comportamiento funcional, detener y volver a SPEC.

## Ambiente de desarrollo y ejecución reproducible
- **Estado real:** [EXISTENTE / FALTA / POR_COMPROBAR].
- **Plataforma/tecnologías:** [PROPUESTA_ARRIBA; NO_TRATAR_COMO_APROBADA_HASTA_GATE_PLAN].
- **Herramientas y dependencias de ejecución/desarrollo:** [ARCHIVOS_Y_VERSIONES_SI_PROCEDE].
- **Instalación/configuración:** [PASOS_REALES_POR_VALIDAR]; no guardar secretos.
- **Arranque visible de la aplicación:** [ARCHIVO_O_COMANDO], [URL_O_PANTALLA_ESPERADA].
- **Diferencias Mac/Windows:** [PASOS_SI_DIFIEREN / IGUALES].
- **Archivos locales excluidos de Git:** [GITIGNORE_O_NO_APLICA].
- **Criterio ambiente listo:** [COMPROBACION_CONCRETA].

## Estrategia obligatoria de pruebas automatizadas
- **Tipo elegido:** [UNITARIA / FUNCIONAL / INTEGRACIÓN / COMBINADAS] y por qué.
- **Runner/herramienta:** [REUTILIZAR_EXISTENTE / PROPONER_OPCIÓN_MÍNIMA_PARA_APROBACIÓN].
- **Ubicación de tests:** [RUTA_PROPUESTA].
- **Preparación de pruebas:** [INSTALACIÓN_FIXTURES_DATOS].
- **Comando reproducible en entorno elegido:** [COMANDO_POR_VERIFICAR]; variantes Mac/Windows si corresponde.
- **Resultado verificable:** [EVIDENCIA_DE_ASSERTS_Y_ESTADO_DEL_COMANDO].
- **Pruebas manuales complementarias:** [ESCENARIOS_DE_EXPLORACION_SI_APLICA].
| Requisito / criterio | Caso automatizado positivo | Negativo/límite | Nivel / ubicación prevista |
|---|---|---|---|
| [RF/CA] | [CASO] | [CASO] | [TIPO/ARCHIVO] |
- **Regresión sobre funciones anteriores:** [CASOS_EXISTENTES / NO_APLICA].
- **Excepción a automatización (solo si es inevitable):** [CAUSA_RIESGO_ALTERNATIVA_Y_APROBACION_EXPRESA].

## README — guía comprobable de inicio y uso
- **Crear o actualizar:** [DECISIÓN].
- **Describir:** qué hace, funciones disponibles, requisitos previos, configuración sin secretos.
- **Iniciar y VER la aplicación:** [PASOS, COMANDO_O_ARCHIVO, URL_O_PANTALLA].
- **Mac/Windows:** [VARIANTES_SI_HAY].
- **Uso, detener servidor y pruebas:** [PASOS_Y_RESULTADO_ESPERADO].
- **Comprobación antes de CLOSE:** [QUIÉN/EVIDENCIA/NO_VERIFICADO].

## Trazabilidad de diseño y pruebas
| RF/CA aprobado | Componente/módulo responsable | Test automatizado previsto y nivel | Observaciones |
|---|---|---|---|
| [RF/CA] | [COMPONENTE] | [NOMBRE_RUTA_NIVEL] | [RIESGO_O_NINGUNO] |

## Riesgos y mitigaciones
- [RIESGO] → [MITIGACIÓN].

## Coherencia SPEC–PLAN
Si surge decisión funcional nueva, DETENER; preguntar, autorizar cambios SPEC y revalidar antes de continuar.

## Aprobación
- **Stack recomendado y estado:** [PROPUESTO / APROBADO_TRAS_DECISIÓN_EXPRESA].
- **Aprobador:** [PENDIENTE / Usuario].
- **Fecha de aprobación:** [PENDIENTE / FECHA_FIABLE / No determinada].
- **Evidencia:** [PENDIENTE / Aprobación explícita del usuario en esta conversación].
> No aprobar PLAN sin decisión tecnológica y estrategia de tests (o excepción expresa). Una vez aprobado, cambiar **Estado de la cabecera** a «Aprobado», guardar y releer para verificar. No generar TASKS en la misma respuesta.
