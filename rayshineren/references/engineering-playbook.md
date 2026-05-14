# Engineering Playbook

Use this file for architecture, implementation, debugging, optimization, and engineering planning.

## General method

RayshineRen's engineering style is evidence-driven:

```text
goal -> minimal runnable path -> check script -> record/log -> benchmark/evaluation -> boundary statement -> next iteration
```

Do not jump from idea to large framework. Prefer a small reproducible experiment with explicit acceptance criteria.

## Local AI / RAG / Agent engineering

Reusable design pattern:

1. Define the task and expected input/output.
2. Decide whether the problem is model inference, retrieval, tool use, evaluation, monitoring, or deployment.
3. Build minimal loop:
   - model endpoint or gateway;
   - data or tools;
   - prompt/structured output;
   - logs and records;
   - fixed test cases.
4. Add engineering layers only when the minimal loop fails:
   - query rewrite if user/document expressions mismatch;
   - hybrid search if dense retrieval misses keywords/IDs/code;
   - rerank if recall is broad but order is poor;
   - context compression if retrieved content is too noisy;
   - evaluation if manual inspection is no longer reliable;
   - monitoring if service health matters.

RAG diagnosis categories:

- parsing/ingestion failure;
- chunking failure;
- sparse/dense retrieval failure;
- rerank failure;
- context construction failure;
- generation/prompt failure;
- evaluation blind spot;
- permission/freshness/data-governance gap.

## AI Infra / performance engineering

Reusable performance investigation chain:

```text
symptom / target metric
  -> reproduce with fixed benchmark
  -> profile at service/runtime/operator level
  -> inspect graph / schedule / call path
  -> isolate hot path with microbenchmark
  -> apply optimization
  -> compare before/after under same conditions
  -> check end-to-end effect and regression risk
```

Common tools and signals:

- `perf` / flamegraph: CPU hot functions.
- `strace`: system calls, scheduler behavior, blocking behavior.
- GDB: call path, template instantiation, memory layout.
- framework runtime traces: request-level inference and operator timelines.
- Benchmark warmup and repeated runs: avoid cold-start artifacts.
- NUMA/HugePages/allocator/threading controls: system-level effects.

Important distinction: microbenchmark gains can be diluted by remote lookup, serialization, scheduler overhead, memory movement, or full serving path bottlenecks. Always separate local kernel speedup from end-to-end user-visible improvement.

## Compiler / systems engineering

Reusable thinking:

- AI compilers and traditional compilers share a language: IR, passes, schedule, codegen, runtime, layout, linking.
- For code-size/RISC-V tasks, inspect driver pipeline, generated assembly, linker relaxation, call conventions, and abstraction overhead.
- For TVM-like tasks, inspect model graph -> high-level IR -> tensor expression/schedule -> low-level IR -> codegen -> runtime.

## Engineering output template

For engineering tasks, produce:

1. Context: closest prior pattern from RayshineRen's profile.
2. Architecture: text diagram or module list.
3. Implementation plan: smallest useful milestones.
4. Acceptance criteria: commands, metrics, expected artifacts.
5. Observability: logs, records, dashboards, profiling hooks.
6. Risks and boundaries: what this does not prove.
7. Next action: first command/file to create or inspect.
