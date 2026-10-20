# inforeadme

Sitio de documentación técnica publicado con GitHub Pages:
**https://gatojustiniano.github.io/inforeadme**

Los documentos se escriben en Markdown y el sitio los muestra sin ningún paso de compilación.

## Estructura

```
index.html      → motor del sitio (no se edita)
index.md        → portada e índice de documentos
acerca.md       → página "Acerca"
.nojekyll       → evita que GitHub Pages procese los .md con Jekyll
assets/img/     → imágenes
docs/<tema>/    → documentos, una carpeta por tema
plantillas/     → plantilla para documentos nuevos
```

## Temas actuales

| Tema | Carpeta |
|------|---------|
| Linux · Servidores | `docs/linux/` |
| Odoo | `docs/odoo/` |
| Laravel | `docs/laravel/` |
| Git | `docs/git/` |
| Guía del sitio | `docs/guia/` |

## Agregar un documento

1. Copia `plantillas/documento.md` a `docs/<tema>/<nombre>.md`.
2. Regístralo en `index.md`:

   ```
   * 2026/10/19: [Título](docs/tema/nombre.md) { #tema, #etiqueta }
   ```

Detalles en [docs/guia/como-agregar-documentos.md](docs/guia/como-agregar-documentos.md).

## Probar en local

```
python -m http.server 8000
```

Luego abre http://localhost:8000.
