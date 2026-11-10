# De prompts a procesos: SDD con GitHub Copilot

**Toolkit reutilizable de agentes, skill, plantillas y controles para trabajar con desarrollo dirigido por especificaciones (*Spec-Driven Development*, SDD) en VS Code.**

El objetivo es pasar de solicitudes aisladas a un proceso documentado y verificable: comprender el requisito, aclararlo, planificar la solución, implementar una tarea a la vez y comprobar los resultados. Los agentes asisten al usuario, pero **no sustituyen su aprobación** en los *Quality Gates*.

[Ir a la instalación](#instalación-en-vs-code-macos-y-windows) · [Ir al flujo con historias de usuario](#flujo-de-trabajo-con-hu) · [Ver instrumentos SDD](#instrumentos-del-proyecto)

## Qué es SDD y cómo se aplica

SDD es un enfoque de trabajo en el que la especificación de lo que debe hacer el software se prepara, revisa y usa como referencia antes de implementar. No depende por sí mismo de un lenguaje, framework, producto o herramienta determinada. En este toolkit se instrumenta mediante **seis actividades por historia**:

| Actividad | Propósito | Resultado principal |
|---|---|---|
| **1. SPECIFY** | Comprender la necesidad y redactar requisitos verificables. | Borrador de `spec.md`. |
| **2. CLARIFY** | Revisar ambigüedades, límites, errores y contradicciones. | Aclaraciones registradas en `spec.md` y aprobación de SPEC. |
| **3. PLAN** | Proponer o reutilizar tecnologías, diseñar componentes y definir pruebas. | `plan.md` aprobado, incluida la decisión técnica. |
| **4. TASKS** | Organizar el trabajo por tareas verificables y dependencias. | `tasks.md` aprobado. |
| **5. IMPLEMENT** | Desarrollar solamente una tarea autorizada, con pruebas reproducibles. | Código, pruebas, documentación y evidencia por tarea. |
| **6. VALIDATE** | Contrastar requisitos y criterios de aceptación con las pruebas ejecutadas. | Informe de cumplimiento y pendientes. |

Antes de la primera historia, un proyecto nuevo pasa por dos **pasos de preparación general**: `docs/constitution.md` (principios) y `AGENTS.md` (instrucciones del repositorio). Cada uno requiere aprobación independiente. Después de VALIDATE puede realizarse el cierre operativo (*CLOSE*) de la historia, con operaciones Git siempre autorizadas por el usuario.

## Contenido real del repositorio

La estructura siguiente corresponde al **toolkit**, no a una aplicación desarrollada con él:

```text
sdd-copilot-toolkit/
├── agents/
│   ├── project-initializer.agent.md
│   └── task-implementer.agent.md
├── sdd-artifacts/
│   ├── SKILL.md
│   ├── templates/
│   │   ├── AGENTS.md
│   │   ├── HU.md
│   │   ├── README.md
│   │   ├── constitution.md
│   │   ├── plan.md
│   │   ├── spec.md
│   │   └── tasks.md
│   └── resources/
│       ├── approval-checklist.md
│       ├── change-control.md
│       ├── clarify-checklist.md
│       ├── planning-checklist.md
│       ├── readme-checklist.md
│       ├── spec-interview-guide.md
│       ├── tasks-checklist.md
│       └── testing-policy.md
├── .gitignore
└── README.md
```

| Elemento | Función |
|---|---|
| [`agents/project-initializer.agent.md`](agents/project-initializer.agent.md) | Examina las historias y el contexto; conduce Constitución, AGENTS, SPECIFY, CLARIFY, PLAN y TASKS. **No implementa código.** |
| [`agents/task-implementer.agent.md`](agents/task-implementer.agent.md) | Implementa una tarea aprobada cada vez; crea y ejecuta pruebas, valida y solicita autorización para acciones Git. |
| [`sdd-artifacts/SKILL.md`](sdd-artifacts/SKILL.md) | Define el procedimiento compartido y enlaza las plantillas y controles que correspondan a cada fase. |
| [`sdd-artifacts/templates/`](sdd-artifacts/templates/) | Modelos para historia de usuario, Constitución, AGENTS, SPEC, PLAN, TASKS y README **del proyecto que se construye**. |
| [`sdd-artifacts/resources/`](sdd-artifacts/resources/) | Guías y listas de verificación para entrevista, CLARIFY, aprobaciones, planificación, pruebas, tareas, README y cambios. |
| `.gitignore` y `README.md` | Archivos propios del repositorio del toolkit. |

> **Importante:** `sdd-artifacts/templates/README.md` es una **plantilla para las aplicaciones futuras**. El `README.md` en la raíz de este repositorio documenta **el toolkit**. Del mismo modo, el archivo generado `AGENTS.md` de cada proyecto no es lo mismo que un agente personalizado `.agent.md`.

## Requisitos previos

- VS Code con acceso a GitHub Copilot Chat y sesión iniciada.
- Acceso al repositorio de soporte: <https://github.com/QualisForge/sdd-copilot-toolkit>.
- Permiso para crear/copiar carpetas dentro del directorio personal del equipo.
- Una carpeta de **proyecto independiente** donde colocar las historias de usuario. **No es necesario copiar allí el toolkit** cuando se instala en el perfil personal.

Las tecnologías de una aplicación futura **no son prerrequisitos universales**: se analizan y aprueban durante PLAN según la historia y el contexto del proyecto.

## Instalación en VS Code (macOS y Windows)

### 1. Descargar los insumos

1. Abre [este repositorio](https://github.com/QualisForge/sdd-copilot-toolkit).
2. En GitHub, selecciona **Code → Download ZIP** y descomprime el archivo. Si ya trabajas con Git, también puedes clonar el repositorio.
3. Confirma que la descarga contiene los dos archivos `.agent.md` y la carpeta `sdd-artifacts/` completa.

### 2. Copiar los agentes al perfil personal

| Sistema | Carpeta de destino |
|---|---|
| **macOS** | `~/.copilot/agents/` |
| **Windows** | `%USERPROFILE%\.copilot\agents\` |

Crea la carpeta si todavía no existe y coloca allí **ambos archivos**, sin cambiar sus nombres: `project-initializer.agent.md` y `task-implementer.agent.md`.

En macOS, desde Finder, pulsa **Cmd + Shift + G** y escribe la ruta. En Windows, abre el Explorador de archivos y pega la ruta en la barra de direcciones.

### 3. Copiar la skill completa

| Sistema | Carpeta final de la skill |
|---|---|
| **macOS** | `~/.copilot/skills/sdd-artifacts/` |
| **Windows** | `%USERPROFILE%\.copilot\skills\sdd-artifacts\` |

Copia la carpeta **`sdd-artifacts` completa** a `skills/`. En su interior deben quedar **al mismo nivel** `SKILL.md`, `templates/` y `resources/`. No copies únicamente `SKILL.md` ni crees una carpeta `sdd-artifacts/sdd-artifacts/` por error.

### 4. Comprobar el reconocimiento en VS Code

1. Abre VS Code y una carpeta de proyecto; en el chat selecciona el entorno **Copilot**.
2. Abre la paleta de comandos: **Cmd + Shift + P** en macOS o **Ctrl + Shift + P** en Windows.
3. Ejecuta **Chat: Open Customizations**. En **Agents**, verifica que aparecen los dos agentes; en **Skills**, busca `sdd-artifacts`.
4. Inicia un chat nuevo y verifica que puedes elegir `project-initializer` desde el selector de agentes. Para comprobar el contenido de la skill, solicita que localice `SKILL.md` y las plantillas correspondientes; revisa la actividad del chat.

La aparición de un agente o skill en el selector **no garantiza que siga las instrucciones**: comprueba su comportamiento con una historia pequeña.

**Ubicaciones alternativas para uso compartido en un repositorio:** `.github/agents/` y `.github/skills/sdd-artifacts/`. Este README prioriza la instalación **personal** para mantener el proyecto de ejemplo con únicamente `HU/` como entrada.

## Flujo de trabajo con `HU/`

### 1. Preparar el proyecto de entrada

Crea una **carpeta distinta del toolkit** y, dentro, únicamente `HU/` con sus archivos de historias. Por ejemplo:

```text
proyecto/
└── HU/
    ├── HU-001.md  # historia de usuario
    └── HU-002.md  # historia de usuario
```

Las anotaciones `# historia de usuario` son explicativas; **no forman parte del nombre de los archivos**. Si tienes las dos historias desde el inicio, procesa primero `HU-001` (historia de usuario) de forma explícita; la segunda queda como entrada disponible, no como autorización para implementarla en paralelo.

### 2. Iniciar la preparación con `project-initializer`

En VS Code, abre **la carpeta `proyecto/`**, selecciona `project-initializer` y escribe:

```text
Inicia SDD para HU/HU-001.md
```

El agente debe inspeccionar las entradas y el contexto. En un proyecto nuevo, prepara **solo** `docs/constitution.md` en borrador y pide aprobación. **No debe crear `AGENTS.md` todavía.**

Una vez revisada y aprobada la Constitución, responde, por ejemplo, `Aprobada la Constitución`. El agente debe **registrar el estado en el mismo archivo, releerlo y detenerse**. En la siguiente interacción pide continuar a `AGENTS.md` y repite el control. Una aprobación no autoriza los documentos siguientes.

### 3. Completar las seis actividades de la primera historia

| Momento | Acción del usuario | Verificación clave |
|---|---|---|
| **SPECIFY** | Responder las preguntas una por una y revisar el borrador `spec.md`. | Requisitos y criterios observables, sin introducir soluciones técnicas no aprobadas. |
| **CLARIFY** | Revisar hallazgos de QA, resolver dudas una por una y aprobar SPEC. | En `spec.md` queda constancia de CLARIFY, y luego estado **Aprobada** registrado y verificado. |
| **PLAN** | Evaluar la propuesta técnica y las pruebas; aprobar el documento. | Stack aprobado, componentes, trazabilidad RF/prueba, preparación del entorno y README previstos. |
| **TASKS** | Revisar tareas, dependencias, criterios «Hecho cuando» y grupos Git; aprobar. | `tasks.md` aprobado, sin código implementado por el inicializador. |
| **IMPLEMENT** | Cambiar a `task-implementer` y autorizar **una tarea identificada** cada vez. | Código y tests automatizados persistentes, resultado real, pausa para autorizar la siguiente tarea. |
| **VALIDATE** | Pedir revisión final requisito por requisito y decidir cierre. | Matriz de criterios, pruebas ejecutadas, regresión y puesta en marcha comprobable. |

**Ejemplos de solicitudes cortas:**

```text
Continúa con la siguiente fase aprobada.
```

```text
Implementa únicamente T001 de la HU-001 aprobada. Ejecuta sus pruebas y detente.
```

```text
Valida la HU-001 requisito por requisito y presenta evidencias y pendientes.
```

Los mensajes anteriores no sustituyen una aprobación explícita. El usuario debe revisar los cambios y autorizar por separado cualquier commit, push, pull request, merge o tag.

### 4. Incorporar `HU-002` (historia de usuario)

Tras completar y validar la primera historia, selecciona de nuevo `project-initializer`:

```text
Inicia SDD para HU/HU-002.md
```

El agente debe **reutilizar** Constitución y `AGENTS.md` aprobados, consultar la implementación y pruebas existentes, y generar **nuevos** `spec.md`, `plan.md` y `tasks.md` para esta historia. CLARIFY y las aprobaciones siguen siendo obligatorios; las pruebas de la nueva funcionalidad deben incluir regresión sobre la anterior. No se reescriben automáticamente historias ya cerradas.

### Estructura final ilustrativa de una aplicación

```text
proyecto/
├── AGENTS.md
├── README.md
├── docs/
│   └── constitution.md
├── HU/
│   ├── HU-001.md
│   └── HU-002.md
├── specs/
│   ├── HU-001/
│   │   ├── spec.md
│   │   ├── plan.md
│   │   └── tasks.md
│   └── HU-002/
│       ├── spec.md
│       ├── plan.md
│       └── tasks.md
├── src/
└── tests/
```

El árbol es **una referencia de resultado**, no un conjunto de carpetas precreadas. Según las reglas del agente, los directorios reales bajo `specs/` pueden usar el patrón `HU-001-[slug]` (identificador más nombre descriptivo), y la ubicación del código y las pruebas depende de la tecnología **aprobada** en PLAN.

## Instrumentos del proyecto

| Instrumento | Dónde se encuentra en el proyecto de aplicación | Función |
|---|---|---|
| `constitution.md` | `docs/constitution.md` | Principios y criterios generales de calidad, con aprobación humana. |
| `AGENTS.md` | Raíz del proyecto | Instrucciones operativas para los agentes en ese proyecto. |
| `HU-001.md` | `HU/` | Entrada original: historia de usuario; se conserva como fuente de requisitos. |
| `spec.md` | `specs/HU-001-[slug]/` | Requisitos funcionales, criterios de aceptación y registro de CLARIFY. |
| `plan.md` | Mismo directorio de historia | Propuesta técnica, ambiente, pruebas y trazabilidad. |
| `tasks.md` | Mismo directorio de historia | Tareas, dependencias, tests, Quality Gates y grupos Git. |
| `README.md` | Raíz del proyecto | Cómo preparar, ejecutar, usar y probar la **aplicación desarrollada**. |

Los nombres `HU-001` y `HU-002` significan **historia de usuario**. Cada historia recibe sus propios documentos SPEC/PLAN/TASKS; Constitución y AGENTS corresponden al proyecto general.

## Controles de calidad y límites

- **No hay avance por silencio.** Toda aprobación es específica, queda registrada en el archivo correspondiente y se verifica antes de cambiar de fase.
- **CLARIFY es una etapa explícita.** Las preguntas iniciales de SPECIFY no sustituyen su auditoría posterior.
- **La tecnología se decide en PLAN.** Si no está fijada, el agente propone alternativas proporcionadas y espera aprobación; no impone un stack al comenzar.
- **Las pruebas automatizadas deben poder repetirse.** PLAN las define, TASKS las organiza y `task-implementer` las implementa y ejecuta. Solo las comprobaciones manuales no constituyen una suite automatizada reutilizable, salvo excepción documentada y aprobada.
- **La guía de la aplicación debe explicar cómo verla funcionar.** El README del proyecto implementado debe reflejar comandos o pasos efectivamente validados.
- **Los agentes no sustituyen la revisión humana.** Revisa el contenido, las evidencias y las operaciones Git antes de autorizarlas.

## Solución de problemas

| Síntoma | Qué comprobar |
|---|---|
| Un agente no aparece en el selector | Ruta y nombre del `.agent.md`, sesión/harness Copilot y errores en **Chat: Open Customizations → Agents**. |
| No aparece `sdd-artifacts` | Que la carpeta contenga `SKILL.md` **junto con** `templates/` y `resources/`, sin carpetas anidadas por error. |
| Solo hay una parte de las plantillas | Volver a copiar **toda** `sdd-artifacts/` desde el repositorio. |
| El agente no encuentra `HU/HU-001.md` | Abrir en VS Code la **raíz del proyecto de aplicación**, no la carpeta del toolkit. Revisar el nombre exacto. |
| Crea `AGENTS.md` antes de aprobar Constitución | Detenerse; comprobar `docs/constitution.md` pendiente, corregir el orden y repetir la prueba en un chat nuevo. |
| Dice «aprobado» pero no cambia el archivo | Revisar los metadatos guardados; pedir verificación del estado y **no avanzar** hasta que el archivo refleje la aprobación. |
| Omite CLARIFY o no planifica tests | No aprobar SPEC/PLAN: solicitar corregir el documento correspondiente con la skill. |
| La aplicación no inicia tras IMPLEMENT | Seguir el README generado para la aplicación y revisar el comando y entorno **aprobados en PLAN**, sin inventar otros. |

## Documentación de referencia

- [Agentes personalizados en VS Code](https://code.visualstudio.com/docs/agent-customization/custom-agents)
- [Ubicaciones y formato de agentes](https://code.visualstudio.com/docs/agents/reference/custom-agent-file-reference)
- [Skills en VS Code](https://code.visualstudio.com/docs/agent-customization/agent-skills)
- [Administración de personalizaciones](https://code.visualstudio.com/docs/agent-customization/overview)

---

Este repositorio **distribuye herramientas y plantillas**; no es una aplicación terminada ni ejecuta por sí solo los proyectos creados con ellas. La implementación, los comandos de pruebas y las instrucciones de arranque dependen de cada historia y del plan técnico aprobado.
