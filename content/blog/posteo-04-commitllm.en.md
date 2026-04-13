+++
title = "CommitLLM: a cryptographic protocol for verifying LLM inference"
description = "Researchers from CCSD and LambdaClass present CommitLLM, a commit-and-audit protocol to verify that a provider actually ran the language model it claims to have run."
date = 2026-04-10
[taxonomies]
tags = ["ccsd", "llm", "cryptography", "research", "lambdaclass"]
+++

Researchers from the Center for Cryptography and Distributed Systems, in collaboration with [LambdaClass](https://lambdaclass.com), present **CommitLLM**: a cryptographic commit-and-audit protocol for verifying inference of open-weight language models.

The work addresses a concrete problem: when a client sends a prompt to a provider that claims to run a specific model — for example, Llama 70B — there is no technical way to verify that those weights were actually used, that decoding was not altered, or that the delivered response was not modified after inference.

CommitLLM proposes a practical approach that avoids the two existing extremes: statistical fingerprinting, which can be fooled, and zero-knowledge proof systems, which are too expensive for real production. The protocol keeps the provider on the normal GPU serving path, without kernel rewriting or proof generation for each response, and allows the client to verify on CPU with bounded overhead.

The paper includes measurements on `Qwen2.5-7B-W8A8`, `Llama-3.1-8B-W8A8`, and `Llama-3.1-70B-W8A8`, with an online tracing overhead between 12 and 14%, and a verification cost of 1.3 ms per token for Llama 70B in a routine CPU audit.

**Authors:** Federico Carrone, Diego Kingston, Manuel Puebla, Mauro Toscano.

---

- [Read the paper](https://raw.githubusercontent.com/lambdaclass/CommitLLM/main/paper/main.pdf)
- [GitHub repository](https://github.com/lambdaclass/CommitLLM)
- [commitllm.com](https://commitllm.com)
