+++
title = "CommitLLM: un protocolo criptográfico para verificar inferencia de LLMs"
description = "Investigadores del CCSD y LambdaClass presentan CommitLLM, un protocolo de commit-and-audit para verificar que un proveedor realmente corrió el modelo de lenguaje que declara haber corrido."
date = 2026-04-10
[taxonomies]
tags = ["ccsd", "llm", "criptografia", "investigacion", "lambdaclass"]
+++

Investigadores del Centro de Criptografía y Sistemas Distribuidos, en colaboración con [LambdaClass](https://lambdaclass.com), presentamos **CommitLLM**: un protocolo criptográfico de commit-and-audit para verificar inferencia de modelos de lenguaje open-weight.

El trabajo aborda un problema concreto: cuando un cliente envía un prompt a un proveedor que declara correr un modelo específico —por ejemplo, Llama 70B—, no tiene forma técnica de verificar que esos pesos fueron realmente utilizados, que el decoding no fue alterado, o que la respuesta entregada no fue modificada después de la inferencia.

CommitLLM propone un enfoque práctico que evita los dos extremos existentes: el fingerprinting estadístico, que puede ser engañado, y los sistemas de pruebas sin divulgación de conocimiento, que son demasiado costosos para producción real. El protocolo mantiene al proveedor en el serving path normal de GPU, sin reescritura de kernels ni generación de pruebas por cada respuesta, y permite al cliente verificar en CPU con overhead acotado.

El paper incluye mediciones sobre `Qwen2.5-7B-W8A8`, `Llama-3.1-8B-W8A8` y `Llama-3.1-70B-W8A8`, con un overhead online de tracing de entre el 12 y el 14%, y un costo de verificación de 1.3 ms por token para Llama 70B en un audit rutinario sobre CPU.

**Autores:** Federico Carrone, Diego Kingston, Manuel Puebla, Mauro Toscano.

---

- [Leer el paper](https://raw.githubusercontent.com/lambdaclass/CommitLLM/main/paper/main.pdf)
- [Repositorio en GitHub](https://github.com/lambdaclass/CommitLLM)
- [commitllm.com](https://commitllm.com)
