# Housefold documentation

This repository holds the platform-level product and architecture documents shared by the Housefold repositories. Component implementation details belong with their code; these documents describe the intent, system boundaries, and shared domain language that those implementations should follow.

## Core documents

- [Project Vision](product/vision.md) — purpose, principles, scope, and initial release outcomes.
- [System Architecture](architecture/system.md) — components, boundaries, data flows, deployment direction, and failure behavior.
- [Domain Model](architecture/domain-model.md) — shared concepts, ownership, relationships, and invariants.

## Status

These are the initial architecture baselines, reconstructed from the Housefold design discussions. Details marked **Open** are not settled contracts. Update these documents when a cross-repository decision changes; record significant decisions in an ADR before implementation depends on them.

Component-specific API contracts and implementation guides should live in the relevant repository and link back here for shared context.
