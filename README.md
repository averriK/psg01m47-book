# Introducción a los Modelos Probabilísticos (PSG-01M47)

**Apuntes de Clase**

Este repositorio contiene las notas de clase del curso de [Introducción a los Modelos Probabilísticos (PSG-01M47)](https://campusposgrado.fi.uba.ar/course/view.php?id=421) dictado por la Dra. Verónica Estela Pastor durante el primer semestre de 2025. Los contenidos están organizados cronológicamente según el orden de las clases.

## Descripción del Proyecto

El libro digital está construido utilizando [Quarto](https://quarto.org/), un sistema de publicación científica y técnica de código abierto que permite crear documentos, libros y sitios web a partir de archivos Markdown y Jupyter Notebooks.

### Estructura del Contenido

- **Idioma principal**: Español (es)
- **Capítulos**: Organizados por fecha de clase (formato YYYYMMDD)
- **Formatos de salida**: HTML y PDF

## Cómo Agregar Nuevos Capítulos

Para agregar un nuevo capítulo al libro, sigue estos pasos:

### 1. Crear el archivo del capítulo

Crea un nuevo archivo `.qmd` en el directorio `psg01m47/es/` con el nombre de fecha correspondiente:

```bash
touch psg01m47/es/YYYYMMDD.qmd
```

### 2. Editar _quarto.yml

Abre el archivo `_quarto.yml` y agrega la nueva entrada en la sección `chapters` bajo `book:`:

```yaml
book:
  title: "Introducción a los Modelos Probabilísticos (PSG-01M47)"
  subtitle: "Apuntes de Clase"
  # ... otras configuraciones ...
  chapters:
    - index.qmd
    - psg01m47/es/20250317.qmd
    - psg01m47/es/20250321.qmd
    # ... capítulos existentes ...
    - psg01m47/es/YYYYMMDD.qmd  # ← Agregar nueva línea aquí
```

### 3. Estructura del archivo de capítulo

Los archivos `.qmd` deben seguir la siguiente estructura básica:

```markdown
# Título del Capítulo

## Introducción

Contenido del capítulo en formato Markdown...

### Subsección

Más contenido, incluyendo:
- Fórmulas matemáticas: $\LaTeX$
- Código (si es necesario)
- Referencias bibliográficas
```

## Personalización de Estilos

### Modificar el tema visual

Edita la sección `format` en `_quarto.yml` para personalizar el tema:

```yaml
format:
  html:
    theme:
      light: cosmo     # Cambia el tema claro
      dark: darkly     # Cambia el tema oscuro
    highlight-style: a11y  # Estilo de resaltado de código
    
    # Configuración de la tabla de contenidos
    toc: true
    toc-location: left    # izquierda, derecha, body
    toc-title: "TOC"
    toc-depth: 3          # profundidad de niveles
    
    # Navegación y búsqueda
    search: true
    page-navigation: true
    
    # Configuración del código
    code-fold: true       # plegado de código
    code-summary: "Source"
    code-line-numbers: false
```

### Opciones de formato comunes

```yaml
format:
  html:
    # Colores y fuentes
    theme: [cosmo, custom.scss]  # combinar temas
    
    # Footer personalizado
    page-footer:
      left: "© 2025 Tu Nombre"
      right: "Powered by Quarto"
    
    # Configuración matemática
    math: mathjax  # o katex
    
    # Enlaces externos
    link-external-newwindow: true
    
  pdf:
    documentclass: scrreprt  # clase de documento LaTeX
    geometry: ["margin=1.1in"]  # márgenes
    number-sections: true
```

## Renderizar el Libro

### Comando básico de renderizado

```bash
quarto render
```

### Renderizar formatos específicos

```bash
# Solo HTML
quarto render --to html

# Solo PDF
quarto render --to pdf

# Vista previa con servidor local
quarto preview
```

### Opciones adicionales

```bash
# Renderizar con limpieza previa
quarto render --clean

# Renderizar archivos específicos
quarto render index.qmd

# Renderizar con verbose output
quarto render --verbose
```

## Estructura de Directorios

```
psg01m47-book/
├── _quarto.yml          # Configuración principal
├── index.qmd            # Página de inicio
├── _build/              # Archivos de construcción
│   └── styles.css       # Estilos personalizados
├── _bib/                # Referencias bibliográficas
│   └── references.bib
├── psg01m47/            # Contenido del curso
│   ├── es/              # Capítulos en español
│   └── en/              # Capítulos en inglés (
└── _publish/            # Archivos generados (HTML, PDF)
```

## Contacto

Para preguntas, sugerencias o colaboraciones, contacta al autor:

**Alejandro Verri Kozlowski**  
📧 [averri@fi.uba.ar](mailto:averri@fi.uba.ar)  
🏛️ Laboratorio de Dinámica de Estructuras  
🎓 Facultad de Ingeniería, Universidad de Buenos Aires (FIUBA)  
📍 Las Heras 2214, Ciudad de Buenos Aires, Argentina

---

*Generado con [Quarto](https://quarto.org/) y chatGPT 4.1*