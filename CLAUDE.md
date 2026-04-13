# CLAUDE.md — academic-digital-skills

## Contexto del proyecto

Este repositorio es una adaptación de
[fralfaro/docencia-digital](https://github.com/fralfaro/docencia-digital),
que está orientado a **académicos y docentes** universitarios.

El objetivo aquí es distinto: crear un **MOOC propedéutico de 20 horas**
dirigido a **estudiantes de 3° y 4° medio / primer año universitario**
que quieran aprender a gestionar su trabajo académico con herramientas digitales.

La propuesta fue postulada a la convocatoria **Aprende USM 2026** bajo el nombre:
> *"Aprende a gestionar tu trabajo académico con herramientas digitales"*

---

## Estado actual del repositorio

> ✅ El material ya fue copiado desde `fralfaro/docencia-digital`.
> **No es necesario clonar nada.** Solo hay que podar y adaptar lo que existe.

Estructura actual confirmada:

```
academic-digital-skills/
├── material/
│   ├── 00_intro/
│   ├── 01_github/
│   ├── 02_colab/
│   ├── 03_latex/
│   └── 04_quarto/
├── slides/
│   ├── .quarto/
│   ├── 00_intro/
│   ├── 01_github/
│   ├── 02_colab/
│   ├── 03_latex/
│   └── 04_quarto/
├── assets/
├── CLAUDE.md
├── _quarto.yml
├── index.qmd
├── light.scss
├── dark.scss
├── custom.scss
├── render_slides.py
└── requirements.txt
```

> ⚠️ **La carpeta `slides/` no se modifica en esta etapa.**
> Contiene presentaciones RevealJS que se trabajarán por separado.
> Enfócate solo en `material/`.

---

## Estructura objetivo del MOOC

El curso tiene **4 módulos** (~5 horas cada uno) + introducción:

| Módulo | Carpeta | Herramienta | Habilidad | Entregable |
|--------|---------|-------------|-----------|------------|
| Intro | `material/00_intro/` | — | Bienvenida y configuración de cuentas | Cuentas creadas y listas |
| 1 | `material/01_github/` | GitHub | Organizar y versionar el trabajo | Repositorio público con README |
| 2 | `material/02_colab/` | Google Colab | Calcular y documentar en la nube | Notebook con análisis simple |
| 3 | `material/03_latex/` | Overleaf / LaTeX | Escribir con formato académico | Informe PDF con portada y secciones |
| 4 | `material/04_quarto/` | Posit Cloud + Quarto | Publicar un portafolio académico | Sitio publicado en Quarto Pub / GitHub Pages |

> ⚠️ **No hay módulo de IA independiente.** La IA (Claude, ChatGPT, Copilot)
> se integra como *tip transversal* al final de cada módulo, no como sección propia.
> Si existe `material/05_ia/`, **eliminarla completamente**.

---

## Mapeo de archivos: qué conservar, renombrar y eliminar

### Módulo 0 — Introducción

| Archivo actual | Acción |
|----------------|--------|
| `material/00_intro/intro.qmd` | Adaptar (ver reglas) |

### Módulo 1 — GitHub

| Archivo actual | Acción | Nombre final |
|----------------|--------|--------------|
| `material/01_github/index.qmd` | Adaptar | `index.qmd` |
| `material/01_github/01_esencial.qmd` | Adaptar | `01_esencial.qmd` |
| `material/01_github/03_automatizacion.qmd` | Adaptar + renombrar (solo sección GitHub Pages) | `02_pages.qmd` |
| `material/01_github/02_colaborativo.qmd` | **ELIMINAR** — ramas, PRs, CI/CD: demasiado avanzado | — |

### Módulo 2 — Google Colab

| Archivo actual | Acción | Nombre final |
|----------------|--------|--------------|
| `material/02_colab/index.qmd` | Adaptar | `index.qmd` |
| `material/02_colab/colab_01_esencial.qmd` | Adaptar + renombrar | `01_esencial.qmd` |
| `material/02_colab/colab_02_pandas.qmd` | Simplificar + renombrar (solo intro, sin profundidad) | `02_practica.qmd` |
| `material/02_colab/colab_03_visualizacion.qmd` | **ELIMINAR** — demasiado disciplinar | — |

### Módulo 3 — Overleaf / LaTeX

| Archivo actual | Acción | Nombre final |
|----------------|--------|--------------|
| `material/03_latex/index.qmd` | Adaptar | `index.qmd` |
| `material/03_latex/overleaf_01_esencial.qmd` | Adaptar + renombrar | `01_esencial.qmd` |
| `material/03_latex/overleaf_03_plantillas.qmd` | Adaptar + renombrar (foco: primer informe) | `02_informe.qmd` |
| `material/03_latex/overleaf_02_matematica.qmd` | **ELIMINAR** — notación avanzada fuera de alcance | — |

### Módulo 4 — Posit Cloud + Quarto

| Archivo actual | Acción | Nombre final |
|----------------|--------|--------------|
| `material/04_quarto/index.qmd` | Adaptar | `index.qmd` |
| `material/04_quarto/quarto_01_intro.qmd` | Adaptar + renombrar | `01_intro.qmd` |
| `material/04_quarto/quarto_02_documentos.qmd` | Adaptar + renombrar + reemplazar RStudio → Posit Cloud | `02_positcloud.qmd` |
| `material/04_quarto/quarto_05_pages.qmd` | Adaptar + renombrar + agregar Quarto Pub | `03_portafolio.qmd` |
| `material/04_quarto/quarto_03_revealjs.qmd` | **ELIMINAR** | — |
| `material/04_quarto/quarto_04_sitios.qmd` | **ELIMINAR** | — |
| `material/04_quarto/quarto_06_flujo.qmd` | **ELIMINAR** | — |

---

## Reglas de adaptación (aplicar a TODOS los archivos)

### 1. Público objetivo
- **Original:** académico/docente universitario
- **Nuevo:** estudiante de 4° medio o primer año universitario, sin experiencia previa

### 2. Cambios de tono y persona
- Cambiar "el docente" / "el académico" → "tú" / "el estudiante"
- Cambiar "tu clase" / "tus estudiantes" → "tu trabajo" / "tus entregables"
- Eliminar referencias a diseño instruccional, syllabus, evaluaciones docentes
- Usar lenguaje directo, motivador y sin jerga técnica innecesaria

### 3. Eliminar secciones avanzadas
Borrar sin dejar rastro:
- Ramas (branches), Pull Requests, merge conflicts
- CI/CD, GitHub Actions
- Expresiones regulares, scripts avanzados de bash
- Notación matemática avanzada (más allá de ecuaciones básicas en LaTeX)
- RAG, agentes IA, Copilot Studio, fine-tuning

### 4. Agregar al final de cada archivo de contenido: tip de IA
Cada archivo `.qmd` de contenido (no los `index.qmd`) debe terminar con:

```markdown
## 💡 Cómo puede ayudarte la IA en este módulo

Puedes apoyarte en herramientas como **ChatGPT**, **Claude** o **GitHub Copilot** para:

- [ejemplo concreto 1 relacionado con la herramienta del módulo]
- [ejemplo concreto 2]
- [ejemplo concreto 3, opcional]

> ⚠️ Recuerda siempre revisar y entender lo que genera la IA antes de usarlo.
```

Ejemplos por módulo:
- **GitHub:** "pedirle que explique un mensaje de error de git", "generar un README para tu proyecto"
- **Colab:** "pedirle que explique una línea de código Python", "generar un ejemplo de gráfico simple"
- **LaTeX:** "pedirle que corrija errores de compilación", "generar la estructura de un informe"
- **Quarto:** "pedirle que convierta un documento Word a formato Quarto .qmd"

### 5. Módulo 4: Posit Cloud en lugar de RStudio Desktop
- Reemplazar toda mención a "instalar R", "instalar RStudio", "RStudio Desktop"
  por **"Posit Cloud (posit.cloud)"**
- Agregar esta nota donde corresponda:

```markdown
> **Nota sobre publicación:** Posit Cloud permite escribir documentos Quarto
> desde el navegador sin instalar nada. Para publicar tu portafolio en línea,
> usaremos **[Quarto Pub](https://quartopub.com)** o **GitHub Pages**, ya que
> la publicación directa desde Posit Cloud no está disponible en Quarto 1.8+.
```

### 6. Entregable concreto en cada `index.qmd` de módulo
Al final del `index.qmd` de cada módulo (no en la intro), incluir:

```markdown
## 🎯 ¿Qué vas a producir en este módulo?

Al terminar este módulo habrás creado:

- **[nombre del entregable]:** [descripción en 1 línea de qué es y para qué sirve]

Este entregable se integrará en tu portafolio académico al final del curso.
```

---

## `_quarto.yml` objetivo

Reemplazar el `_quarto.yml` actual con este contenido exacto:

```yaml
project:
  type: book
  output-dir: docs
  render:
    - "index.qmd"
    - "material/00_intro/intro.qmd"
    - "material/01_github/*.qmd"
    - "material/02_colab/*.qmd"
    - "material/03_latex/*.qmd"
    - "material/04_quarto/*.qmd"

book:
  title: "Aprende a gestionar tu trabajo académico con herramientas digitales"
  subtitle: "MOOC propedéutico — Aprende USM 2026"
  author: "Francisco Alfaro Medina & Patricio Olivares Roncagliolo"
  date: "2026"
  favicon: "assets/img/brand/brand__usm.png"
  repo-url: "https://github.com/fralfaro/academic-digital-skills"
  sidebar:
    logo: "assets/img/icon/icon__notebook-hat.png"

  chapters:
    - index.qmd
    - part: "Introducción"
      chapters:
        - material/00_intro/intro.qmd
    - part: material/01_github/index.qmd
      chapters:
        - material/01_github/01_esencial.qmd
        - material/01_github/02_pages.qmd
    - part: material/02_colab/index.qmd
      chapters:
        - material/02_colab/01_esencial.qmd
        - material/02_colab/02_practica.qmd
    - part: material/03_latex/index.qmd
      chapters:
        - material/03_latex/01_esencial.qmd
        - material/03_latex/02_informe.qmd
    - part: material/04_quarto/index.qmd
      chapters:
        - material/04_quarto/01_intro.qmd
        - material/04_quarto/02_positcloud.qmd
        - material/04_quarto/03_portafolio.qmd

lang: es

format:
  html:
    theme:
      light: [flatly, light.scss]
      dark: [darkly, dark.scss]
    number-sections: false
    toc: true
    page-layout: full
```

---

## Instrucción de inicio para Claude Code

Pega esto al abrir Claude Code en este repositorio:

```
Lee el CLAUDE.md completo. El material ya está copiado en material/.
No necesitas clonar nada externo.

Tu tarea es podar y adaptar lo existente. Trabaja módulo por módulo,
empezando por el Módulo 1 (material/01_github/).

Antes de modificar cualquier archivo, muéstrame el plan:
- qué archivos vas a eliminar
- qué archivos vas a renombrar
- qué cambios de contenido harás en cada uno

Espera mi confirmación antes de ejecutar.
```

---

## Notas finales

- La carpeta `slides/` **no se toca** en esta etapa — es trabajo posterior
- El sitio se publica en GitHub Pages desde la carpeta `docs/`
- URL final esperada: `fralfaro.github.io/academic-digital-skills`
- Agregar `docs/` al `.gitignore` solo si se prefiere no versionar el build;
  de lo contrario, GitHub Pages lo necesita en el repo
