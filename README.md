# SPM Noticias

Un experimento de blog de noticias en línea construido como **sitio estático**: sin base de datos, sin servidor y sin panel de administración. Todo el contenido vive en archivos Markdown dentro de este repositorio y se convierte en HTML en cada publicación.

🌐 **Sitio:** https://arthursstrong.github.io/hugo-spmnoticias/

## ¿Por qué un sitio estático?

La idea del proyecto es probar qué tan lejos se puede llevar un blog de noticias con el enfoque más simple posible:

- **Gratis de hospedar:** GitHub Pages sirve el sitio sin costo.
- **Rápido y seguro:** solo se sirven archivos HTML y CSS, no hay nada que hackear ni mantener en un servidor.
- **Contenido versionado:** cada artículo es un archivo en git, con historial completo de cambios.
- **Publicación automática:** hacer push a `main` compila y publica el sitio.

## Tecnologías

- [Hugo](https://gohugo.io/) (extended) como generador de sitios estáticos.
- [Ananke](https://github.com/theNewDynamic/gohugo-theme-ananke) como tema, incluido como submódulo de git.
- [GitHub Actions](https://docs.github.com/actions) + [GitHub Pages](https://pages.github.com/) para compilar y publicar.

## Estructura

```
.
├── archetypes/        # Plantilla para artículos nuevos
├── content/posts/     # Artículos en Markdown
├── themes/ananke/     # Tema (submódulo)
├── hugo.toml          # Configuración del sitio
└── .github/workflows/ # Workflow de compilación y publicación
```

## Uso local

Requisitos: Hugo extended 0.160 o superior y git.

```bash
# Clonar con el tema incluido
git clone --recurse-submodules https://github.com/ArthurSStrong/hugo-spmnoticias.git
cd hugo-spmnoticias

# Servidor de desarrollo con recarga automática (incluye borradores)
hugo server -D
```

El sitio queda disponible en http://localhost:1313/hugo-spmnoticias/.

## Escribir un artículo

```bash
hugo new content posts/titulo-del-articulo.md
```

Esto crea el archivo con `draft: true`. Escribe el contenido en Markdown y cambia a `draft: false` cuando esté listo para publicarse.

## Publicación

Cada push a `main` ejecuta el workflow `.github/workflows/gh-pages.yml`, que compila el sitio con Hugo y lo publica en GitHub Pages. Los pull requests solo compilan el sitio para verificar que no haya errores, sin publicarlo.

## Estado

Proyecto experimental y personal. El contenido es de prueba y puede cambiar o desaparecer en cualquier momento.
