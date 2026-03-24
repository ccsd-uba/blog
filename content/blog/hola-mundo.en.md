+++
title = "Hello World: First steps with Zola"
description = "An introduction to Zola, the static site generator written in Rust that we use for this blog."
date = 2026-03-18
updated = 2026-03-18

[taxonomies]
tags = ["zola", "rust", "meta"]

[extra]
+++

Welcome to our blog! This is the first post, where we explain why we chose Zola to build this site.

## What is Zola?

[Zola](https://www.getzola.org/) is a static site generator written in **Rust**. It's extremely fast, has zero external dependencies (a single binary), and uses [Tera](https://tera.netlify.app/) as its template engine (very similar to Jinja2).

Some reasons why we chose it:

- **Single binary**: no Node.js, no Ruby, no Python. Just `zola build`.
- **Speed**: builds large sites in milliseconds.
- **Native syntax highlighting** with [Syntect](https://github.com/trishume/syntect).
- **Sass** compiled out of the box.
- **Shortcodes** to extend Markdown.

## Installation

```bash
# macOS with Homebrew
brew install zola

# Linux (download the binary)
wget https://github.com/getzola/zola/releases/download/v0.19.2/zola-v0.19.2-x86_64-unknown-linux-gnu.tar.gz
tar -xzf zola-*.tar.gz -C ~/.local/bin

# Windows with Scoop
scoop install zola
```

## Project structure

```
my-blog/
├── config.toml          # Main configuration
├── content/             # Your posts in Markdown
│   ├── _index.md
│   └── blog/
│       ├── _index.md
│       └── hello-world.md
├── templates/           # HTML templates (Tera)
│   ├── base.html
│   ├── index.html
│   └── blog/
│       ├── section.html
│       └── page.html
└── static/              # Static files (CSS, images)
    └── css/
        └── style.css
```

## Basic commands

```bash
# Local server with live reload
zola serve

# Production build
zola build

# Check the project
zola check
```

Coming soon, we'll write about the complete deployment process on Cloudflare Pages or Netlify.
