# OpenLLaMA 7B v2 throughput profile

Exact verified Q4_0 GGUF, CPU-only, 4 threads, pp128/tg16, batch 32, F16 KV.

- Prefill: 33478.30 ms
- Decode total: 7156.81 ms
- Projection kernels: 39615.24 ms (97.5% of profiled model time)
- FFN GEMM: 24682.91 ms (62.3% of projection-kernel time)
- Non-GEMM core residual: 1019.38 ms
- Dominant component: ffn_gemm_ms (24682.91 ms)
- Dominant profiled kernel kind: ffn_down (8673.32 ms)
- Peak RSS: 3819160 KiB
- Page faults: major=1, minor=94652
- Process CPU: 231%

This profile selects the next optimization target; it is not a universal throughput claim.
