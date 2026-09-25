# Public Roadmap

This roadmap describes validation priorities rather than promises or release dates.

## Current position — V4

The current private prototype has established much of the control-plane architecture:

```text
Telemetry
   ↓
Context / Workload
   ↓
Task / Intent
   ↓
Prediction / Policy
   ↓
Validation
   ↓
Runtime Binding
   ↓
Execution
   ↓
Readback / Verification
   ↓
Rollback / SafeMode / Feedback
```

The next phase is intentionally less focused on adding abstractions and more focused on proving real-world usefulness.

## Priority 1 — reproducible benchmark harness

Create controlled AICore OFF vs. AICore ON experiments for representative workloads:

- compilation;
- rendering;
- local AI inference;
- gaming;
- mixed interactive workloads.

Measure, where appropriate:

- task completion time;
- latency;
- throughput;
- frame-time / 1% low metrics;
- CPU/GPU/NPU utilization;
- power;
- energy per task;
- temperature;
- responsiveness.

## Priority 2 — cross-hardware validation

Validate behavior on multiple modern PC configurations rather than inferring compatibility from one development machine.

Target categories include:

- AMD-based AI PCs;
- Intel-based AI PCs;
- systems with supported discrete GPUs;
- later, additional NPU/platform ecosystems.

## Priority 3 — heterogeneous compute integration

Strengthen the gap between abstract routing decisions and real capability-gated CPU/GPU/NPU execution.

Important goals:

- explicit vendor/runtime capability discovery;
- safe fallback;
- readback where supported;
- clear separation between routing, execution, and measured effect.

## Priority 4 — workload/policy evidence

Build a reproducible dataset around:

```text
workload context
+ machine capabilities
+ telemetry
+ selected policy
+ observed outcome
```

The purpose is to evaluate whether adaptive policy produces repeatable benefit, not merely to increase model complexity.

## Priority 5 — public demonstration surface

Provide a safe demonstration that can expose:

- telemetry;
- workload transitions;
- proposed policy;
- validation;
- simulated or explicitly labeled native execution;
- verification;
- rollback/SafeMode events.

Any demonstration must clearly label simulation versus native platform behavior.

## Long-term research direction

AICore's longer-term research direction is a vendor-neutral control plane capable of coordinating workload intent and heterogeneous compute while remaining observable, capability-aware, and reversible.

That direction remains a research/product objective until supported by real cross-platform evidence.
