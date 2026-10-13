# OpenLLaMA 7B FFN kernel repeated same-runner A/B

Current baseline vs candidate on the exact same runner and verified Q4_0 GGUF; 3 alternating-order pairs.

Hosted-runner regression tolerance: 2.0% for FFN and end-to-end time; pull requests and manual runs remain blocking, while main pushes retain evidence without re-rejecting already-merged code.

| Metric | Baseline mean ± SD | Candidate mean ± SD | Improvement |
|---|---:|---:|---:|
| FFN GEMM ms | 34689.96 ± 1472.36 | 30293.53 ± 215.50 | 12.67% |
| Prefill ms | 45760.00 ± 2277.85 | 41425.20 ± 252.86 | 9.47% |
| Decode ms | 11621.30 ± 31.23 | 9539.43 ± 105.37 | 17.91% |
| QKV ms | 13158.29 ± 581.72 | 11666.14 ± 82.89 | 11.34% |

- Total improvement: 11.18%
- FFN improvement: 12.67%
- RSS growth: 0.22%
- Gate: **PASS**
- Gate enforcement: **evidence-only on main push**
