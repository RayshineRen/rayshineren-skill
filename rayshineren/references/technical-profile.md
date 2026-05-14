# Technical Profile

## One-line positioning

RayshineRen is best represented as a research-oriented AI systems engineer who connects AI4Science research, LLM/RAG application engineering, AI infrastructure, compiler/runtime/operator optimization, and hardware-aware performance analysis.

## Staged technical arc

| Stage | Core focus | Reusable capability |
|---|---|---|
| Undergraduate foundations | linear algebra, classical search, reinforcement learning, PDE basics, Java Web, RISC-V/IC practice, HPC/container basics | turn mathematical and system concepts into working programs; build broad CS foundations |
| Graduate research | AI4PDE, PINN/DeepONet/FNO/PeRCNN, AI systems, compilers, RISC-V code-size optimization, simulation, mathematical logic | formulate research questions, read papers, reproduce methods, identify failure modes, design experiments |
| 2023 LLM exploration | LLaMA/Vicuna/FastChat, DeepSpeed, Milvus/RAG, long context, Whisper, search-enhanced LLM demos | understand LLM as a system of model + retrieval + context + service + tools, not a single model call |
| AI Infra / performance engineering | TVM, Eigen/KDNN, TensorFlow custom ops, fused embedding ops, recommendation serving, bRPC, KV Cache, ARM NEON/SVE, NUMA | trace performance from application to model graph, operators, runtime, instructions, cache, and system topology |
| Local AI engineering practice | local model service stack, vLLM/llama.cpp/Ollama/LiteLLM/Open WebUI, embedding, Qdrant, RAG, tool calling, evaluation, monitoring | build runnable, observable, reproducible AI engineering loops with explicit acceptance criteria |

## Technical themes

### AI4PDE / AI4Science

- PINN family: PINN, MHPINN, EmPINN, gPINN, VPINN, XPINN, SA-PINN, FB-PINN.
- Operator learning: DeepONet, physics-informed DeepONet, FNO, neural operators.
- Discrete and spatiotemporal PDE solvers: PeRCNN, PhyCRNet, ConvLSTM, autoregressive/attention-enhanced variants.
- Research taste: focus on loss imbalance, training instability, long-time extrapolation, weak baselines, and engineering validation.

### LLM / RAG / AI application engineering

- LLM deployment and service stack: FastChat, vLLM, llama.cpp, Ollama, LiteLLM, OpenAI-compatible APIs, Open WebUI.
- RAG components: document parsing, chunking, embedding, dense retrieval, BM25, hybrid search, rerank, query rewrite, context compression, citation, evaluation.
- AI app primitives: token/context budgeting, embedding similarity, prompt comparison, structured output, tool calling, minimal evaluation sets.

### AI Infra / performance

- Framework and compiler chain: TensorFlow/PyTorch/JAX/MindSpore concepts, TVM Relay/TIR/TOPI/LLVM, GraphExecutor, PackedFunc.
- Operator optimization: softmax, GEMM, fused embedding ops, FusedMatMul, custom ops, TensorFlow Grappler.
- Runtime/system: bRPC serving, recommendation-system embedding lookup, Cuckoo Hash/FastKV, locks, thread pools, KV Cache.
- Hardware-aware optimization: ARM NEON/SVE/SME, cache hierarchy, NUMA, HugePages, allocator choices, perf/strace/GDB.

## Personal method

- Start with a map, not an implementation.
- Prefer one minimal runnable artifact over many unverified concepts.
- Record what ran, what failed, and what remains unknown.
- Evaluate with fixed cases and measurable signals.
- Treat “demo works” as the beginning, not the end.
