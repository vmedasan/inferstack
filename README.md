# InferStack

**InferStack** is an engineering project focused on understanding and building infrastructure for production LLM inference.

The project will evolve from a simple inference service into a Kubernetes-native distributed serving platform used to study performance, reliability, autoscaling, observability, and cost.

## Why This Project Exists

Running an ML model locally is very different from operating it as a reliable production service.

Production AI infrastructure must answer questions such as:

- How should inference requests be scheduled?
- What happens to latency as concurrency increases?
- How can batching improve throughput without hurting tail latency?
- When should inference workers scale up or scale down?
- How efficiently are compute resources being utilized?
- How should traffic be routed across multiple inference workers?
- What happens when a worker fails?
- How should infrastructure telemetry influence scaling decisions?
- How does model-serving architecture affect cost per request or token?

InferStack is intended to explore these questions through reproducible engineering experiments.

## Engineering Questions

The project will progressively measure and analyze:

- P50, P95, and P99 request latency
- throughput
- concurrency
- queue depth
- batching behavior
- compute and GPU utilization
- autoscaling behavior
- failure recovery
- model-serving performance
- infrastructure cost

## Planned Architecture

The platform will gradually evolve toward:

```text
Client
  |
  v
API Gateway
  |
  v
Request Scheduler
  |
  v
Inference Engine
  |
  v
Kubernetes Workers
```

Supporting components will eventually include:

- metrics
- logs
- distributed tracing
- autoscaling
- load generation
- benchmarking
- failure testing
- infrastructure as code

## Technology Direction

The project is expected to incorporate:

**Python · Go · Kubernetes · Docker · PyTorch · vLLM · Ray/KubeRay · Prometheus · Grafana · OpenTelemetry · OpenTofu**

Technologies will be introduced only when they solve a concrete engineering problem in the platform.

## Project Phases

### Phase 1 — Foundations

Build and containerize a minimal inference gateway and deploy it locally.

### Phase 2 — Model Serving

Integrate PyTorch and a production-oriented inference engine.

### Phase 3 — Observability

Measure request latency, throughput, queue depth, and infrastructure telemetry.

### Phase 4 — Distributed Inference

Introduce multiple workers, routing, distributed execution, and failure handling.

### Phase 5 — Adaptive Infrastructure

Experiment with autoscaling, scheduling, and Kubernetes-native control logic.

### Phase 6 — Benchmarking

Produce reproducible performance and cost comparisons across serving configurations.

## Current Status

**Day 1 — Environment and repository foundation**

The development environment, repository structure, and initial engineering roadmap are currently being established.

No benchmark or performance claims are published yet.

Future results will include methodology, configuration details, and reproducible evidence.

## Engineering Principles

InferStack will prioritize:

- reproducibility
- measurable performance
- reliability
- observable systems
- automated testing
- clear design decisions
- evidence over claims
