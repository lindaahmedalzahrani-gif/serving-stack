# Capacity note (team, one page)

## The numbers

- Locked model: Qwen/Qwen2.5-1.5B-Instruct (fp16 fallback; AWQ scored 7/10, below 8/10 threshold)
- Target p95 end-to-end latency: 2.5 seconds
- Knee concurrency: 8
- Tokens per second at the knee: 373.54
- Max sustainable request rate: 2.92 req/s (approx)

## The limiting family

Compute-bound: throughput scales nearly linearly with concurrency (62 to 590 tok/s
across levels 1 to 16), indicating spare GPU compute capacity is being effectively
utilized. Latency grows gradually rather than spiking sharply, consistent with
the system not yet hitting a hard saturation point within this sweep.

## Why the knee, not the peak

The knee reflects real, honest capacity within our latency SLO. Peak throughput
(589.89 tok/s at concurrency 16) ignores that p95 latency
has risen to 2.6387 seconds, exceeding what we can promise users.
