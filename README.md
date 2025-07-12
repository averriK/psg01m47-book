# Libro Quarto: Instrucciones de uso

Repositorio: [https://github.com/averriK/psg01m47-book](https://github.com/averriK/psg01m47-book)  
Este repositorio contiene un libro técnico estructurado en Quarto Markdown, sin dependencias de R, Python ni IDEs externos.

---

## 1. Clonar el repositorio

Clona el proyecto con `git` desde la terminal:
```sh
git clone https://github.com/averriK/psg01m47-book.git
cd psg01m47-book
```
> Si no tienes git instalado:  
> - [Descargar git](https://git-scm.com/downloads)

---

## 2. Instalar Quarto

El único requisito es [Quarto](https://quarto.org/).  
Descarga la versión adecuada desde la [página oficial de Quarto](https://quarto.org/docs/get-started/).

Confirma que la instalación es correcta:
```sh
quarto --version
```
Debe mostrar un número de versión (por ejemplo, `1.5.55`).  
Si el comando no es reconocido, revisa la instalación y el PATH según la [guía oficial](https://quarto.org/docs/get-started/).

---

## 3. Estructura del proyecto

- Todos los **capítulos** se encuentran en la carpeta `_chapters/`, en archivos `.qmd`.
- El archivo principal del libro es `index.qmd` (en la raíz).
- El archivo de configuración general es `_quarto.yml`.
- El resultado renderizado (HTML final) se genera en `_publish/` por configuración del proyecto.

---

## 4. Renderizar el libro

Para compilar el libro y generar la salida HTML, ejecuta:
```sh
quarto render
```
Esto generará el archivo `_publish/index.html`, que es la versión navegable del libro.

- Para visualizar el resultado, abre `_publish/index.html` en cualquier navegador web moderno.
- Si prefieres generar una presentación (revealjs), asegúrate que la configuración de formato en `_quarto.yml` esté habilitada para revealjs y ejecuta el mismo comando.

Referencias útiles:
- [Render de proyectos Quarto](https://quarto.org/docs/projects/quarto-projects.html)
- [Soporte para libros y capítulos](https://quarto.org/docs/books/)

---

## 5. Editar capítulos existentes

- Edita cualquier archivo `.qmd` en `_chapters/` con tu editor de texto preferido (VSCode, Sublime, nano, etc.).
- Guarda los cambios y ejecuta nuevamente `quarto render` para actualizar el HTML.

> **Tip:**  
> Si agregas ecuaciones LaTeX, revisa la [documentación de matemáticas en Quarto](https://quarto.org/docs/authoring/markdown-basics.html#mathematics) para asegurar compatibilidad.

---

## 6. Agregar un capítulo nuevo

1. **Crea** un archivo `.qmd` en `_chapters/` (ejemplo: `_chapters/capitulo_nuevo.qmd`).
2. Usa como plantilla otro capítulo, respetando el formato Markdown y los metadatos YAML (si los hay).
3. **Actualiza el índice**:  
   Abre `index.qmd` y agrega la ruta relativa del nuevo archivo bajo la sección `chapters:`. Ejemplo:

```yaml
chapters:
  - _chapters/introduccion.qmd
  - _chapters/capitulo_nuevo.qmd
```

4. Guarda y vuelve a ejecutar `quarto render`.

> Si el nuevo capítulo no aparece en el libro, es porque NO fue listado en `index.qmd`.  
> Si lo eliminas, recuerda quitarlo también del índice.

---

## 7. Eliminar un capítulo

- Borra el archivo correspondiente en `_chapters/`.
- Quita la referencia del archivo en la sección `chapters:` de `index.qmd`.
- Renderiza nuevamente el libro.

---

## 8. Revisión y publicación local

- El producto final es el archivo `_publish/index.html`.
- No busques el HTML en la raíz: siempre se genera en la carpeta definida en `_quarto.yml` (por defecto, `_publish/`).
- Si necesitas compartir el libro, puedes comprimir la carpeta `_publish/` o alojarla en un servidor web.

---

## 9. Recursos y referencias

- [Documentación oficial Quarto](https://quarto.org/docs/)
- [Libros y capítulos en Quarto](https://quarto.org/docs/books/)
- [Referencia Markdown en Quarto](https://quarto.org/docs/authoring/markdown-basics.html)
- [Opciones de output (HTML, revealjs, etc)](https://quarto.org/docs/output-formats/html-basics.html)
- [Configuración avanzada de proyectos](https://quarto.org/docs/projects/quarto-projects.html)

---

## 10. Créditos, licencia y contacto

- Autor/revisor: [TI994/A]  
- Para soporte, abrir un [Issue en GitHub](https://github.com/averriK/psg01m47-book/issues)
- (Agrega aquí licencia o créditos si corresponde)

