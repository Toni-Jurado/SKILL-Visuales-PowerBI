
# Repositorio con SKILL de diseño de Visuales para Power BI

![SKILLs PowerBI](https://img.shields.io/badge/SKILLs%20PowerBI-green?style=for-the-badge)

Repositorio de **Skills** orientadas a ayudarnos a generar visuales de Power BI apoyados en Agentes e IA.

Estas SKILLs contienen instrucciones, procedimientos, ejemplos y recursos que pueden ser utilizados por agentes compatibles para crear visuales de Power BI.

\---

## Requisitos

Antes de utilizar las SKILLs de este repositorio se recomienda disponer de:

* Visual Studio Code actualizado.
* Git instalado.
* Acceso al modo Agent de GitHub Copilot.
* El repositorio descargado o clonado en el equipo local.

Puedes comprobar que Git está instalado ejecutando:

```bash
git --version
```

\---

# 1\. Clonar este repositorio

Selecciona la carpeta de tu equipo donde quieras almacenar el repositorio y ejecuta:

```bash
git clone https://github.com/Toni-Jurado/SKILL-Visuales-PowerBI.git
```

Accede posteriormente a la carpeta:

```bash
cd SKILL-Visuales-PowerBI
```

Y ábrela en Visual Studio Code:

```bash
code .
```

También puedes realizar la clonación directamente desde Visual Studio Code mediante:

```text
Source Control
→ Clone Repository
```

\---

# 2\. Estructura de una SKILL

Cada SKILL debe encontrarse dentro de su propia carpeta.

Por ejemplo:

```text
skills/
├── pbi-columnas-verticales/
│   └── SKILL.md
│
├── pbi-grafico-de-linea/
│   └── SKILL.md
│
└── pbi-treemap/
    └── SKILL.md
```

El archivo principal debe llamarse obligatoriamente:

```text
SKILL.md
```

Una SKILL puede contener además otros recursos:

```text
pbi-columnas-verticales/
├── SKILL.md
├── ejemplos/
│   ├── barra-de-progreso.md
│   └── tarjeta-kpi.md
├── plantillas/
│   └── medida.tmdl
└── scripts/
```

Estos archivos pueden ser consultados por el agente cuando la propia SKILL indique que son necesarios, por tanto, son importantes y deben mantenerse dentro de la carpeta de la SKILL.

\---

# 3\. Cómo utilizar las SKILLs dentro de un proyecto

Las SKILLs pueden estar disponibles únicamente dentro de un proyecto concreto o bien de forma global para todos los proyectos.

## 3.1. Utilizar las SKILLs en un proyecto específico

Si quieres que las SKILLs estén disponibles **únicamente** dentro de un proyecto concreto, debes copiarlas dentro del proyecto.

VS Code reconoce varias ubicaciones para SKILLs de proyecto.

La ubicación recomendada para proyectos que utilizan GitHub Copilot es:

```text
<RutaDeTuProyecto>.github/skills/
```

Por ejemplo:

```text
MiProyectoPowerBI/
│
├── .github/
│   └── skills/
│       ├── pbi-columnas-verticales/
│       │   └── SKILL.md
│       │
│       └── pbi-grafico-de-linea/
│           └── SKILL.md
│
├── README.md
└── ...
```

Copia las carpetas de las SKILLs que quieras utilizar dentro de:

```text
.github/skills/
```

El resultado debe seguir siempre este patrón:

```text
.github/
└── skills/
    └── nombre-skill/
        └── SKILL.md
```

No copies únicamente el archivo `SKILL.md`.

Debes copiar la carpeta completa de la SKILL, ya que puede contener referencias, scripts o ejemplos adicionales.

## 3.2. Utilizar las SKILLs en todos los proyectos

Si quieres utilizar las SKILLs en **todos tus proyectos**, no es necesario copiarlas dentro de cada repositorio.

Puedes instalarlas como SKILLs personales.

En Windows, la ubicación recomendada para GitHub Copilot es:

```text
C:\\Users\\<TU\_USUARIO>\\.copilot\\skills\\
```

Equivale a:

```text
\~/.copilot/skills/
```

Por ejemplo:

```text
C:\\Users\\<TU\_USUARIO>\\.copilot\\skills\\
│
├── pbi-columnas-verticales/
│   └── SKILL.md
│
├── pbi-grafico-de-linea/
│   └── SKILL.md
│
└── pbi-treemap/
    └── SKILL.md
```

De esta forma las SKILLs estarán disponibles para GitHub Copilot independientemente del proyecto que abras en VS Code.

\---

## 4\. Comprobar que VS Code detecta las SKILLs

Después de copiar las SKILLs en la ubicación correspondiente, es recomendable comprobar que VS Code las reconoce. Para esto, debes realizar los siguientes pasos:

1. Abre Visual Studio Code.
2. Abre GitHub Copilot Chat y escribe:

```text
/skills
```

VS Code mostrará el menú de configuración de SKILLs disponibles.

También puedes acceder desde:

```text
Copilot Chat
→ Configure Chat
→ Skills
```

Comprueba que aparecen las SKILLs instaladas.

Si acabas de copiar las SKILLs y no aparecen inmediatamente, recarga la ventana de Visual Studio Code:

```text
Ctrl + Shift + P
```

Ejecuta:

```text
Developer: Reload Window
```

\---

## 5\. Cómo utiliza Copilot una SKILL

Normalmente no es necesario indicar explícitamente qué SKILL debe utilizar.

GitHub Copilot analiza:

* El nombre de la SKILL.
* Su descripción.
* La tarea solicitada.
* El contexto actual del proyecto.

Cuando considera que una SKILL es relevante, puede cargar sus instrucciones automáticamente.

Por ejemplo, si existe una SKILL especializada en generar visuales de columnas agrupadas y solicitas:

```text
Crea un gráfico de columnas agrupadas que muestre las ventas por país.
```

Copilot puede identificar la SKILL correspondiente y utilizar sus instrucciones para resolver la tarea.

Por este motivo es especialmente importante que el archivo `SKILL.md` tenga una descripción clara y específica.

\---

# 9\. Invocar una SKILL manualmente

Las SKILLs también pueden utilizarse como comandos desde Copilot Chat cuando están disponibles.

Por ejemplo, dependiendo del nombre definido por la SKILL:

```text
/powerbi-svg
```

seguido de la petición:

```text
Crea una barra horizontal SVG que represente
la venta actual y marque con una línea vertical
el valor del año anterior.
```

La disponibilidad mediante `/` depende de la configuración y versión de GitHub Copilot utilizada.

Puedes consultar las SKILLs reconocidas escribiendo:

```text
/skills
```

\---

# 10\. SKILLs de proyecto vs SKILLs personales

Existen dos formas principales de trabajar con las SKILLs.

|Tipo|Ubicación|Uso|
|-|-|-|
|Proyecto|`.github/skills/`|Solo disponibles para ese proyecto|
|Personal|`\~/.copilot/skills/`|Disponibles para todos los proyectos|

## SKILLs de proyecto

Recomendadas cuando:

* La SKILL pertenece específicamente a un proyecto.
* Forma parte de las reglas del repositorio.
* Debe compartirse con todo el equipo.
* Debe versionarse junto al código.

Ejemplo:

```text
.github/skills/powerbi-project-rules/
```

## SKILLs personales

Recomendadas cuando:

* Utilizas frecuentemente la misma SKILL.
* Trabajas en varios proyectos Power BI.
* No quieres duplicarla en cada repositorio.
* Quieres mantener una biblioteca personal de capacidades para Copilot.

Ejemplo:

```text
\~/.copilot/skills/powerbi-svg/
```

\---

# 11\. Otras ubicaciones compatibles

VS Code también puede reconocer SKILLs almacenadas en:

```text
.github/skills/
.claude/skills/
.agents/skills/
```

para SKILLs asociadas al proyecto.

Y:

```text
\~/.copilot/skills/
\~/.claude/skills/
\~/.agents/skills/
```

para SKILLs personales.

Para un entorno basado principalmente en **VS Code + GitHub Copilot**, este repositorio recomienda utilizar:

```text
.github/skills/
```

para proyectos y:

```text
\~/.copilot/skills/
```

para SKILLs globales.

Esto hace más evidente qué agente o entorno constituye el destino principal de la configuración.

\---

# 12\. Configurar una ubicación personalizada

VS Code permite definir ubicaciones adicionales para buscar Agent Skills mediante la configuración:

```text
chat.agentSkillsLocations
```

Esta opción puede ser útil si quieres mantener una biblioteca central de SKILLs sin copiarlas a:

```text
\~/.copilot/skills/
```

Por ejemplo, podrías mantener todas tus SKILLs en:

```text
C:\\AI\\skills\\
```

y configurar VS Code para utilizar esa ubicación.

Esta estrategia puede ser interesante para equipos que gestionan una biblioteca compartida de Agent Skills.

\---

# 13\. Actualizar las SKILLs

Si clonaste este repositorio mediante Git, puedes actualizarlo fácilmente.

Accede a la carpeta:

```bash
cd C:\\GitHub\\SKILL-Visuales-PowerBI
```

Y ejecuta:

```bash
git pull
```

Esto descargará la versión más reciente de las SKILLs.

Si las tienes copiadas en:

```text
\~/.copilot/skills/
```

deberás volver a copiar las SKILLs actualizadas.

Por ejemplo:

```powershell
Copy-Item `
    ".\\skills\\\*" `
    "$HOME\\.copilot\\skills\\" `
    -Recurse `
    -Force
```

\---

# 14\. Mantener las SKILLs sincronizadas con Git

Una alternativa más avanzada consiste en clonar directamente el repositorio y utilizar una ubicación personalizada mediante:

```text
chat.agentSkillsLocations
```

De esta forma puedes tener:

```text
GitHub
   │
   │ git pull
   ▼
C:\\GitHub\\SKILL-Visuales-PowerBI
   │
   │
   ▼
Visual Studio Code
   │
   ▼
GitHub Copilot
```

Esto evita mantener varias copias de las mismas SKILLs.

Al ejecutar:

```bash
git pull
```

las SKILLs locales quedan actualizadas directamente.

\---

# 15\. Crear una nueva SKILL

Para crear una nueva SKILL, crea una carpeta:

```text
mi-nueva-skill/
```

y dentro:

```text
SKILL.md
```

Por ejemplo:

```text
skills/
└── powerbi-dax-review/
    └── SKILL.md
```

El archivo `SKILL.md` debe contener un bloque YAML inicial.

Ejemplo básico:

```markdown
---
name: powerbi-dax-review
description: Revisa y optimiza medidas DAX utilizadas en modelos de Power BI.
---

# Power BI DAX Review

Utiliza esta SKILL cuando sea necesario analizar,
corregir u optimizar código DAX.

## Instrucciones

1. Analiza la medida DAX proporcionada.
2. Identifica errores funcionales.
3. Evalúa problemas de rendimiento.
4. Propón una versión optimizada.
5. Explica los cambios realizados.
```

El nombre de la SKILL debe ser descriptivo.

Se recomienda utilizar:

```text
minúsculas-con-guiones
```

Por ejemplo:

```text
powerbi-svg
powerbi-theme
powerbi-dax
powerbi-modeling
powerbi-visual-design
```

\---

# 16\. Buenas prácticas

Al utilizar o desarrollar Agent Skills:

* Mantén cada SKILL centrada en una capacidad concreta.
* Utiliza nombres claros y descriptivos.
* Define claramente cuándo debe utilizarse una SKILL.
* Evita instrucciones innecesariamente extensas.
* Separa ejemplos y documentación extensa en archivos adicionales.
* Mantén los recursos relacionados dentro de la carpeta de la SKILL.
* Versiona las SKILLs mediante Git.
* Documenta cambios importantes.
* Revisa una SKILL descargada de terceros antes de utilizarla.
* Revisa especialmente cualquier script que pueda ejecutar comandos sobre el equipo local.

\---

# 17\. Compatibilidad

Las Agent Skills utilizan un estándar abierto diseñado para facilitar su reutilización entre diferentes agentes y herramientas compatibles.

Dependiendo de la herramienta utilizada, pueden existir diferencias en:

* Ubicación de las SKILLs.
* Detección automática.
* Invocación manual.
* Ejecución de scripts.
* Acceso a herramientas externas.
* Gestión del contexto.

Este repositorio está diseñado principalmente pensando en:

```text
Visual Studio Code
+
GitHub Copilot
+
Copilot Agent Mode
```

\---

# 18\. Configuración recomendada

Para la mayoría de usuarios que quieran reutilizar estas SKILLs en diferentes proyectos de Power BI, la configuración recomendada es:

```text
GitHub
│
└── SKILL-Visuales-PowerBI
        │
        └── skills
              │
              ├── skill-1
              ├── skill-2
              └── skill-3

                    │
                    │ copiar
                    ▼

C:\\Users\\TU\_USUARIO\\.copilot\\skills\\
                    │
                    ├── skill-1
                    ├── skill-2
                    └── skill-3
```

Después:

```text
VS Code
→ GitHub Copilot
→ Agent Mode
→ /skills
```

y comprobar que las SKILLs han sido detectadas.

\---

# 19\. Flujo recomendado para trabajar con este repositorio

```text
1. Clonar repositorio

        ↓

2. Revisar las SKILLs disponibles

        ↓

3. Seleccionar las que necesites

        ↓

4. Copiarlas a \~/.copilot/skills/

        ↓

5. Abrir VS Code

        ↓

6. Comprobarlas con /skills

        ↓

7. Utilizarlas desde Copilot Agent Mode
```

\---

# Seguridad

Una Agent Skill puede incluir instrucciones para ejecutar herramientas, scripts o comandos.

Antes de instalar una SKILL de terceros:

1. Revisa el contenido de `SKILL.md`.
2. Revisa los scripts incluidos.
3. Comprueba qué comandos puede solicitar ejecutar.
4. Verifica qué archivos puede modificar.
5. No habilites aprobaciones automáticas de comandos que no hayas revisado.

El hecho de que una SKILL esté disponible públicamente no implica que deba ejecutarse sin revisión previa.

\---

# Contribuciones

Las mejoras y nuevas SKILLs son bienvenidas.

El flujo recomendado es:

```bash
git checkout -b nueva-skill
```

Realiza los cambios:

```bash
git add .
```

Crea el commit:

```bash
git commit -m "Add new Power BI skill"
```

Sube la rama:

```bash
git push -u origin nueva-skill
```

Y crea posteriormente un **Pull Request** desde GitHub.

\---

# Licencia

Consulta el archivo `LICENSE` del repositorio para conocer las condiciones de utilización, modificación y distribución del contenido.

\---

# Referencias

* Visual Studio Code — Agent Skills  
https://code.visualstudio.com/docs/agent-customization/agent-skills
* Visual Studio Code — Custom Instructions  
https://code.visualstudio.com/docs/agent-customization/custom-instructions
* GitHub Docs — Adding Agent Skills for GitHub Copilot  
https://docs.github.com/en/copilot/how-tos/copilot-on-github/customize-copilot/customize-cloud-agent/add-skills
* GitHub Docs — Copilot Customization  
https://docs.github.com/en/copilot

