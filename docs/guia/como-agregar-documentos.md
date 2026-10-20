# Cómo agregar documentos

Este sitio se genera solo a partir de archivos Markdown. **No hace falta tocar `index.html`.**

## Estructura del repositorio

```
index.html      → motor del sitio (no se edita)
index.md        → portada e índice de documentos
acerca.md       → página "Acerca"
assets/img/     → imágenes
docs/<tema>/    → documentos, una carpeta por tema
plantillas/     → plantilla para documentos nuevos
```

## Agregar un documento

1. Copia `plantillas/documento.md` a `docs/<tema>/<nombre-del-documento>.md`.
   * Nombres en minúsculas, sin espacios ni tildes, separados por guiones: `servidor-dns.md`.
2. Escribe el contenido. El primer encabezado (`# Título`) es el título del documento.
3. Regístralo en `index.md`, en la sección de su tema, con este formato **exacto**:

```
* 2026/10/19: [Título del documento](docs/tema/archivo.md) { #tema, #etiqueta }
```

* La **primera etiqueta** es el tema: agrupa el documento en el menú lateral.
* Las demás etiquetas son opcionales.
* Agrega `#destacado` si quieres usar la sección de destacados (`featured` en `nav-group`).

## Agregar un tema nuevo

1. Crea la carpeta `docs/<tema-nuevo>/`.
2. En `index.md`, agrega un encabezado `## Tema nuevo` y debajo las líneas de sus documentos.

## Rutas de enlaces e imágenes

Todos los documentos se muestran desde la raíz del sitio, así que las rutas **siempre son desde la raíz**:

* Enlace a otro documento: `[Servidor web](docs/linux/servidor-web.md)`
* Imagen: `![descripción](assets/img/mi-imagen.png)`

## Opciones de la portada

En la cabecera de `index.md`:

| Opción | Uso |
|--------|-----|
| `title` / `subtitle` | Título y subtítulo del sitio |
| `nav-group` | Secciones del menú lateral: `temas`, `featured`, `new-N`, `tags`, `months` |
| `nav-width` | Ancho del menú lateral |
| `menu` | Enlaces del menú superior |
| `theme` | `dark` para usar siempre el modo oscuro |

## Parámetros de URL

* `?post=docs/linux/servidor-dns.md` abre un documento.
* `?tag=linux` lista los documentos con esa etiqueta.
* `?month=2024-10` lista los documentos de un mes.
* `?theme=dark` activa el modo oscuro.

## Probar en local

El sitio carga los archivos con peticiones HTTP, así que no funciona abriendo `index.html` con doble clic. Levanta un servidor en la carpeta del repositorio:

```
python -m http.server 8000
```

y abre `http://localhost:8000`.
