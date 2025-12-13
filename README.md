# SHOKUNIN ENGINE
> 改善 (Kaizen) — continuous, incremental improvement.

A workflow orchestration engine forged from deliberate practice: derive → prove → implement → break → fix → ship.

---

## Core Philosophy
I challenged myself to build a workflow engine. Not “learn and build,” but **build, get stuck, and learn**.

This repository is an ambitious long-term forge:
- **One engine**: evolving from toy to production-grade.
- **Six gates**: each with a hard pass/fail bar.
- **No skipping**: prove correctness before scaling complexity.

---

## The Rules of Engagement
1. **No Gate Skipping**: I do not proceed to the next phase until the current gate is passed.
2. **Prove Before Implement**: diagrams + proofs first, then code.
3. **Break It On Purpose**: every gate should be validated through tests.
4. **No Tutorial Hell**: reference docs are allowed. However, copying code/solutions is not.
5. **Ship It**: every phase ends with working code and a demo.

---

## Project Structure
```txt
shokunin-engine/
├── docs/
│   ├── phase-1-proof.md          # Proofs + invariants (living)
│   ├── architecture.md           # System overview (living)
│   └── decisions/                # ADRs (Architecture Decision Records)
├── core/                         # Gate 1: in-memory DAG executor
├── plugins/                      # Gate 2: plugin system + integrations
├── distributed/                  # Gate 3: queue + persistence + scaling
├── ml/                           # Gate 4: embeddings + vector search + streaming
├── observability/                # Gate 5: tracing + metrics + alerting
├── platform/                     # Gate 6: UI + hardware hooks + perf
└── examples/
    └── llm-workflow.json         # Example workflows
```

---

## The Six Gates

### Gate 1: The Foundation

#### Build: 
A simple DAG executor that runs workflows in-memory.

#### What you prove:
- Why workflows are Directed Acyclic Graphs (topological sort proof).
- Prove that your execution order is correct (graph theory).
- Why async execution matters (demonstrate with blocking vs non-blocking I/O math).

#### Critical concepts to internalize:
- State machines (draw the state diagram, prove it's deterministic).
- Dependency resolution (implement topological sort from scratch).
- Concurrency vs. parallelism (measure it, don't just read about it).

### Gate 2: The Integration

#### Build:
A plugin system + 5 integrations.

#### What you prove:
- Why plugin architectures use interfaces/traits (prove with dependency inversion).
- Rate limiting algorithms (derive token bucket from first principles).
- Exponential backoff math (prove convergence).

#### Critical concepts to internalize:
- API contract design (OpenAPI, but understand WHY).
- Circuit breaker pattern (derive the state transitions).
- Idempotency (prove your operations are idempotent).

### Gate 3: The Distribution

#### Build:
A message queue-based execution + persistence + horizontal scaling.

#### What you prove:
- CAP theorem (prove you can't have all three, pick your tradeoffs).
- Why eventual consistency works (derive it from distributed systems theory).
- Message ordering guarantees (prove FIFO, at-most-once, at-least-once, exactly-once).

#### Critical concepts to internalize:
- Event sourcing (derive state from events, prove it's correct).
- Distributed consensus (understand Raft/Paxos, even if you don't implement).
- Database design for workflows (prove your schema supports the queries you need).

### Gate 4: The Intelligence

#### Build:
A machine learning model integration + vector database + streaming workflows.

#### What you prove:
- Why embeddings work (understand the math, cosine similarity proof).
- Streaming vs. batch processing tradeoffs (prove with queueing theory).
- Memory management for large payloads (prove your allocator is efficient).

#### Critical concepts to internalize:
- Model serving patterns (sync vs. async, prove latency/throughput tradeoffs).
- Vector similarity search (understand HNSW, even if you use a library).
- Backpressure handling (derive it from queueing theory).

### Gate 5: The Observability

#### Build:
A distributed tracing + metrics + logging + alerting.

#### What you prove:
- Why sampling is necessary (prove with information theory).
- SLO/SLI/SLA math (derive error budgets).
- Percentiles vs. averages (prove why p99 matters more).

#### Critical concepts to internalize:
- Distributed tracing (understand trace context propagation).
- Time-series databases (prove your retention policy is optimal).
- Anomaly detection (basic statistics, Z-scores, prove it works).

### Gate 6: The Mastery

#### Build:
A UI + IoT/hardware hooks + performance optimization + **(challenge to be decided)**.

#### What you prove:
- Why certain data structures are cache-friendly (prove with hardware specs).
- WebSocket vs. HTTP/2 vs SSE (prove tradeoffs with network theory).
- Your unique contribution (something novel YOU figured out).

#### Critical concepts to internalize:
- Real-time communication patterns.
- Hardware integration protocols (MQTT, gRPC).
- Performance optimization (you can implement it in C if needed, profile-guided).

> This repo was designed to make me uncomfortable. Gate 3 will hurt, and Gate 5 will make me question my sanity. But on the other side, I'll be THE Engineer companies fight for!
