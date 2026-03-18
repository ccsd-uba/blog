+++
title = "Entendiendo Ownership en Rust"
description = "Una guía práctica sobre el modelo de ownership de Rust: qué es, cómo funciona y por qué importa para escribir código seguro y eficiente."
date = 2026-03-10

[taxonomies]
tags = ["rust", "programación", "sistemas"]

[extra]
+++

El sistema de **ownership** es quizás la característica más distintiva de Rust. Es lo que le permite garantizar seguridad de memoria *sin* garbage collector.

<!-- more -->

## ¿Qué es ownership?

En Rust, cada valor tiene un único **dueño** (owner). Cuando el dueño sale de scope, el valor se libera automáticamente. Sin GC, sin `free()` manual.

Hay tres reglas fundamentales:

1. Cada valor tiene exactamente un owner.
2. Solo puede haber un owner a la vez.
3. Cuando el owner sale de scope, el valor se destruye.

## Un ejemplo simple

```rust
fn main() {
    let s1 = String::from("hola");
    let s2 = s1; // s1 se mueve a s2

    // Esto causaría un error de compilación:
    // println!("{}", s1); // error: value moved

    println!("{}", s2); // OK
}
```

A diferencia de lenguajes como Python o Java, aquí no hay dos referencias al mismo string. El valor se **movió** de `s1` a `s2`.

## Borrowing: prestando sin ceder el ownership

Si querés usar un valor sin transferir la propiedad, usás referencias:

```rust
fn main() {
    let s1 = String::from("mundo");
    let len = calcular_largo(&s1); // prestamos s1
    println!("Largo de '{}': {}", s1, len); // s1 sigue siendo válido
}

fn calcular_largo(s: &String) -> usize {
    s.len()
}
```

El `&` indica que es una **referencia** (borrow). La función `calcular_largo` puede usar `s` pero no tiene ownership sobre él.

## Referencias mutables

```rust
fn main() {
    let mut s = String::from("hola");
    agregar_mundo(&mut s);
    println!("{}", s); // "hola, mundo"
}

fn agregar_mundo(s: &mut String) {
    s.push_str(", mundo");
}
```

Regla importante: **solo puede existir una referencia mutable a la vez** en el mismo scope. Esto previene data races en tiempo de compilación.

## ¿Por qué esto importa?

Este sistema hace que Rust sea increíblemente seguro: imposible tener dangling pointers, use-after-free, o data races — y todo detectado en compile-time, sin costo en runtime.

En el próximo post voy a hablar sobre **lifetimes**, que son la extensión natural de este sistema para manejar referencias con distintos tiempos de vida.
