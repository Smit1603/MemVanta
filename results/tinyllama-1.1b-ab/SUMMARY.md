# TinyLlama 1.1B Q4_0 — MemVanta vs llama.cpp

Same GGUF, CPU-only, 4 threads, pp512/tg128, context 768, batch 32, F16 KV, 5 repetitions.

- MemVanta pp: 18.93 ± 0.03 tok/s
- llama.cpp pp: 79.21 ± 0.24 tok/s
- MemVanta tg: 6.67 ± 0.02 tok/s
- llama.cpp tg: 48.39 ± 0.13 tok/s
- MemVanta peak RSS: 644168 KiB
- llama.cpp peak RSS: 1190380 KiB
- MemVanta RSS reduction: 45.89%
