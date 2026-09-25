# Safety and Control Principles

AICore is designed around the assumption that system-control decisions can be wrong, stale, unsupported, or fail during execution.

## 1. AI is advisory

AI output is not treated as privileged authority.

```text
AI / Prediction
      ↓
Proposal
      ↓
Policy
      ↓
Validator
      ↓
Executor
```

## 2. Capabilities are explicit

A policy can request an abstract behavior, but execution is allowed only when the active platform/provider declares the necessary capability.

Unsupported hardware should fail closed or degrade to a supported path rather than pretending execution succeeded.

## 3. Freshness matters

System state can change faster than a slow inference provider can respond. Prepared decisions therefore need time/freshness semantics.

A stale policy should not become valid simply because it was generated successfully.

## 4. Execution and verification are separate

A requested operation is not equivalent to an observed result.

AICore's architecture distinguishes:

```text
Requested state
      ↓
Execution result
      ↓
Observed/read-back state
```

This distinction enables post-condition checks and avoids representing an attempted operation as verified success.

## 5. Failure is a normal state

The architecture includes explicit concepts for:

- failed execution;
- unsupported execution;
- no-op behavior;
- rollback;
- degraded operation;
- SafeMode;
- recovery.

## 6. Model/simulation evidence is labeled

Model and simulated-platform modes are intentionally separated from native platform execution.

Simulation is useful for verifying orchestration and failure handling. It is not hardware certification and cannot establish real performance effects.

## 7. Local-first control

The project is designed around local system context and local control boundaries. Optional local AI providers can assist with intent or prediction, but the deterministic policy/control boundary remains independent of any single model provider.

## Security scope

The private architecture includes security boundaries around:

- IPC;
- application identity and permissions;
- contract validation;
- policy validation;
- plugins;
- runtime execution;
- configuration;
- persistent data.

Security properties that depend on a specific operating-system identity setup, deployment configuration, signing system, or production hardware backend require separate target-environment validation.
