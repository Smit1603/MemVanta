# OpenLLaMA 7B FFN tuning

Exact verified Q4_0 GGUF, CPU-only, 4 threads, pp128/tg16, F16 KV.

| Mode | Batch | Prefill ms | Decode ms | FFN ms | Total ms | Peak RSS KiB |
|---|---:|---:|---:|---:|---:|---:|
| fp32 | 16 | 41534.90 | 8874.38 | 31012.47 | 50409.28 | 3815012 |
| fp32 | 32 | 46777.80 | 8861.06 | 34518.25 | 55638.86 | 3818960 |
| fp32 | 64 | 50579.80 | 8851.03 | 36955.79 | 59430.83 | 3827212 |
| q8act | 32 | 90616.50 | 8794.11 | 63485.14 | 99410.61 | 3819380 |
| q8act | 64 | 90692.00 | 8869.58 | 63611.93 | 99561.58 | 3828324 |
| q8act | 16 | 90908.00 | 8828.54 | 63618.79 | 99736.54 | 3815244 |

Best FP32: batch 16; best Q8-act: batch 32.
Q8-act end-to-end improvement vs best FP32: **-97.21%**.
Q8-act FFN improvement vs best FP32: **-104.71%**.
Q8-act peak-RSS delta: **0.11%**.
Promotion gate (>=3% total, FFN faster, <=2% RSS growth, exact deterministic output): **FAIL**.

A failed promotion gate is valid negative evidence; do not enable Q8 activations by default from this workflow alone.
