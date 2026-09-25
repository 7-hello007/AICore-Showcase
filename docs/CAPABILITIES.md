# Capabilities

The table below distinguishes **implemented engineering areas** from **product claims**. AICore V4 is a private prototype; hardware behavior varies by platform and capability.

| Area | V4 engineering status | Important boundary |
|---|---|---|
| System telemetry | Implemented | Coverage depends on OS/hardware |
| Workload/context representation | Implemented | Recognition quality is not presented as a public benchmark |
| Policy generation/resolution | Implemented | Policy generation does not guarantee platform support |
| Policy validation | Implemented | Required before supported actuation |
| Process priority | Native control path exists | Platform/permission dependent |
| CPU affinity | Native control path exists | Platform/permission dependent |
| Power profile | Native platform path exists | OS/capability dependent |
| Background throttling | Implemented through supported policy/control mechanisms | Not a claim of arbitrary hard CPU quota enforcement |
| GPU telemetry | Implemented for supported/vendor-dependent paths | Not universal |
| GPU control | Partial / capability-gated | No universal cross-vendor actuation claim |
| NPU capability/routing | Architecture implemented | Real NPU actuation remains incomplete |
| AI-assisted policy proposal | Implemented | AI is advisory, not privileged authority |
| Local LLM intent interpretation | Implemented optional path | Converts intent into validated semantic proposal; not direct actuation |
| Task contracts | Implemented | Application integration mechanism |
| L0/L1/L2 tiers | Implemented architecture | L2 is not a claim of kernel scheduler replacement |
| Execution readback | Implemented | Depends on available platform/provider readback |
| Rollback / SafeMode | Implemented architecture and tested paths | Hardware-specific certification remains separate |
| Memory/history | Implemented | Effectiveness learning is not yet supported by a public prospective dataset |
| Plugin framework | Implemented | Production hardware plugins/readback require separate validation |
| Local IPC | Implemented | Security certification remains environment-specific |
| Dashboard / CLI | Implemented | Primarily engineering/observability surfaces |
| Model mode | Implemented | Does not perform or prove native hardware actuation |
| Simulated platform | Implemented | In-memory/captured-fixture evidence only |

## Native control vs. model/simulation

AICore deliberately maintains separate evidence categories.

### Model mode

Used to exercise policy/model paths without treating the result as real hardware control.

### Simulated-platform mode

Uses captured platform fixtures and in-memory state to exercise control-loop behavior, readback, rollback, and failure paths without writing to the host.

### Platform mode

Uses platform adapters and may reach real operating-system resource controls. This mode requires target-machine review and authorization.

A successful model or simulated execution must never be reported as a native hardware performance result.

## AI role

AICore can use AI/prediction for:

- workload or intent interpretation;
- policy proposal;
- prediction/preparation.

AI does not receive an unrestricted route to privileged system APIs.

```text
AI / Prediction
      ↓
Proposal
      ↓
Policy
      ↓
Validation
      ↓
Capability binding
      ↓
Execution
      ↓
Readback
```

## Current evidence gap

AICore does not yet publish statistically credible cross-hardware evidence for:

- performance uplift;
- latency reduction;
- energy reduction;
- battery-life improvement;
- thermal improvement;
- gaming FPS improvement;
- AI inference acceleration.

Those are future measurement targets, not current claims.
