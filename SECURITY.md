# Security

This repository contains **public documentation only** and does not contain the private AICore implementation.

Please do not use public issues to disclose suspected security vulnerabilities involving a private AICore build, private binary, or non-public deployment.

If you have been given authorized access to a private AICore build and believe you have found a security issue, contact the repository owner privately using the contact method on their GitHub profile.

## Public architecture security principles

AICore's architecture is designed around:

- explicit identity and permission boundaries;
- contract validation;
- policy validation;
- capability-gated execution;
- separation of AI proposal from privileged authority;
- post-condition/readback verification;
- failure, rollback, degradation, and SafeMode paths;
- clear separation of model/simulation evidence from native platform evidence.

Security properties that depend on a specific deployment environment require validation in that environment.
