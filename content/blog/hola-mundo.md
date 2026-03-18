+++
title = "Hola Mundo: Primeros pasos con Zola"
description = "Una introducción a Zola, el generador de sitios estáticos escrito en Rust que uso para este blog."
date = 2026-03-18
updated = 2026-03-18

[taxonomies]
tags = ["zola", "rust", "meta"]

[extra]
+++

¡Bienvenido a mi blog! Este es el primer post, donde cuento por qué elegí Zola para armar este sitio.

## ¿Qué es Zola?

[Zola](https://www.getzola.org/) es un generador de sitios estáticos escrito en **Rust**. Es extremadamente rápido, tiene cero dependencias externas (un único binario) y usa [Tera](https://tera.netlify.app/) como motor de templates (muy similar a Jinja2).

Algunas razones por las que lo elegí:

- **Un solo binario**: sin Node.js, sin Ruby, sin Python. Solo `zola build`.
- **Velocidad**: construye sitios grandes en milisegundos.
- **Syntax highlighting** nativo con [Syntect](https://github.com/trishume/syntect).
- **Sass** compilado out of the box.
- **Shortcodes** para extender el Markdown.

## Instalación

```bash
# macOS con Homebrew
brew install zola

# Linux (descarga el binario)
wget https://github.com/getzola/zola/releases/download/v0.19.2/zola-v0.19.2-x86_64-unknown-linux-gnu.tar.gz
tar -xzf zola-*.tar.gz -C ~/.local/bin

# Windows con Scoop
scoop install zola
```

## Estructura del proyecto

```
mi-blog/
├── config.toml          # Configuración principal
├── content/             # Tus posts en Markdown
│   ├── _index.md
│   └── blog/
│       ├── _index.md
│       └── hola-mundo.md
├── templates/           # Templates HTML (Tera)
│   ├── base.html
│   ├── index.html
│   └── blog/
│       ├── section.html
│       └── page.html
└── static/              # Archivos estáticos (CSS, imgs)
    └── css/
        └── style.css
```

## Comandos básicos

```bash
# Servidor local con live reload
zola serve

# Build de producción
zola build

# Verificar el proyecto
zola check
```

Próximamente voy a escribir sobre el proceso completo de deployment en Cloudflare Pages o Netlify.
