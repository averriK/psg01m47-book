# Libro Quarto: Instrucciones de uso

Repositorio: [https://github.com/averriK/psg01m47-book](https://github.com/averriK/psg01m47-book)

Este repositorio contiene un libro técnico estructurado en Quarto Markdown, sin dependencias de R, Python ni IDEs externos.  
Incluye soporte para ecuaciones LaTeX y manejo de bibliografía con BibLaTeX.


## 1. Clonar el repositorio

Clona el proyecto con git desde la terminal:

```sh
git clone https://github.com/averriK/psg01m47-book.git
cd psg01m47-book
```
Si no tienes git instalado:  
- [Descargar git](https://git-scm.com/downloads)


## 2. Instalar Quarto

El único requisito es [Quarto](https://quarto.org/).  
Descarga la versión adecuada desde la [página oficial de Quarto](https://quarto.org/docs/get-started/).

Verifica la instalación:

```sh
quarto --version
```


## 3. Estructura del proyecto

- Todos los **capítulos** se encuentran en la carpeta `_chapters/`, en archivos `.qmd`.
- El archivo principal del libro es `index.qmd` (en la raíz).
- El archivo de configuración general es `_quarto.yml`.
- El archivo de referencias bibliográficas está en `_bib/references.bib`.
- El resultado renderizado (HTML final) se genera en `_publish/` por configuración del proyecto.


## 4. Renderizar el libro

Para compilar el libro y generar la salida HTML, ejecuta:

```sh
quarto render
```

Esto generará el archivo `_publish/index.html`, que es la versión navegable del libro.

Para visualizar el resultado, abre `_publish/index.html` en cualquier navegador web moderno.


## 5. Agregar, editar o eliminar capítulos

- Edita cualquier archivo `.qmd` en `_chapters/` con tu editor de texto preferido.
- Para agregar un capítulo, crea un nuevo archivo `.qmd` en `_chapters/` y agrégalo a la lista `chapters:` en `index.qmd`.  
- Para eliminar, borra el archivo en `_chapters/` y elimínalo de la lista en `index.qmd`.
- Siempre ejecuta `quarto render` después de cambios estructurales.

Ejemplo de sección chapters en index.qmd:

```yaml
chapters:
  - _chapters/introduccion.qmd
  - _chapters/capitulo_nuevo.qmd
```


## 6. **Citas y bibliografía en Quarto Markdown**

El sistema de citas utiliza el archivo `_bib/references.bib`, que debe estar referenciado en el YAML del libro o del capítulo.

### a) **Agregar una cita en markdown**

1. **Asegúrate de que el YAML del archivo `.qmd` incluya:**

```yaml
---
bibliography: _bib/references.bib
---
```

2. **Sintaxis para citar en el texto:**

- Para citar un trabajo individual:  
  `[@clave]`  
  Ejemplo:  
  ```
  Según la metodología propuesta por [@smith2020], se obtiene...
  ```
  Renderiza como:  
  Según la metodología propuesta por (Smith, 2020), se obtiene...

- Para citar varios trabajos:  
  `[@clave1; @clave2; @clave3]`  
  Ejemplo:  
  ```
  Varios enfoques han sido sugeridos [@smith2020; @doe2019].
  ```

- Para citar fuera del paréntesis, usar el nombre:  
  ```
  @smith2020 argumenta que...
  ```

- Para agregar una página o localizador:  
  ```
  [@smith2020, p. 15]
  ```

- Para citar como nota al pie:  
  ```
  Blah blah. ^[@smith2020]
  ```

### b) **Ejemplo de bloque completo en un capítulo .qmd**

```markdown
---
title: "Ejemplo de cita"
bibliography: _bib/references.bib
---

El método propuesto por [@timoshenko1953] es aún la referencia estándar en análisis estructural clásico.

Como señala @newmark1965, la respuesta a cargas dinámicas depende de varios factores.

Se pueden encontrar otros enfoques en [@seed1970; @idc2022].

Blah blah. ^[@kramer1996]
```

---

## 7. **Actualizar el archivo de citas `_bib/references.bib`**

El archivo `_bib/references.bib` contiene las referencias en formato **BibLaTeX** (no BibTeX clásico; la diferencia es relevante en campos avanzados, pero el formato base es compatible).

### a) **Agregar una nueva referencia**

1. Abre `_bib/references.bib` en un editor de texto.

2. Agrega la entrada siguiendo la sintaxis estándar.  
   Cada referencia comienza con `@TIPO{clave, ...}` donde **TIPO** puede ser `article`, `book`, `inproceedings`, etc.

#### Ejemplo de entrada `article`:

```bibtex
@article{seed1970,
  author    = {H. B. Seed and I. M. Idriss},
  title     = {Soil moduli and damping factors for dynamic response analyses},
  journal   = {Report No. EERC 70-10},
  year      = {1970},
  address   = {University of California, Berkeley}
}
```

#### Ejemplo de entrada `book`:

```bibtex
@book{kramer1996,
  author    = {Steven L. Kramer},
  title     = {Geotechnical Earthquake Engineering},
  publisher = {Prentice Hall},
  year      = {1996},
  address   = {Upper Saddle River, NJ}
}
```

#### Ejemplo de entrada `inproceedings`:

```bibtex
@inproceedings{idc2022,
  author    = {Juan Pérez and Ana López},
  title     = {Modelos probabilistas para respuesta sísmica},
  booktitle = {Congreso Internacional de Ingeniería Sísmica},
  year      = {2022},
  address   = {Buenos Aires, Argentina}
}
```

### b) **Notas sobre la edición del archivo**

- La **clave** (por ejemplo, `kramer1996`) es lo que usarás en el markdown para citar: `[@kramer1996]`.
- No repitas claves; cada una debe ser única.
- Todos los campos son sensibles a errores de sintaxis (comas, llaves).
- Si usas un gestor de referencias (Zotero, JabRef, Mendeley), puedes exportar entradas en formato BibLaTeX.
- Puedes comentar líneas usando el símbolo `%` al inicio de la línea.


## 8. **Referenciar correctamente el archivo de citas en el libro**

Asegúrate de que tu archivo principal (`index.qmd`) o cada capítulo incluya la línea:

```yaml
bibliography: _bib/references.bib
```
Esto puede estar en el YAML global del libro o en cada capítulo individual.


## 9. **Visualización y verificación de las citas**

- Renderiza el libro con `quarto render`.
- Abre `_publish/index.html` y verifica que las citas aparezcan correctamente (nombres, años, formato de referencias).
- Al final del libro/capítulo, debe aparecer la lista de referencias automáticamente.


## 10. Recursos

- [Quarto: Citas y bibliografía](https://quarto.org/docs/authoring/footnotes-and-citations.html)
- [BibLaTeX documentation](https://ctan.org/pkg/biblatex?lang=en)
- [Guía Markdown en Quarto](https://quarto.org/docs/authoring/markdown-basics.html)


## 11. Contacto y licencia

- Autor/revisor: Verónica Pastor
- Para soporte, abrir un [Issue en GitHub](https://github.com/averriK/psg01m47-book/issues)
