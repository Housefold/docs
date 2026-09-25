# Housefold documentation

This repository holds the platform-level product and architecture documents shared by the Housefold repositories. The three source documents are kept verbatim under their supplied filenames. Component implementation details belong with their code; these documents describe the intent, system boundaries, and shared domain language that those implementations should follow.

## Core documents

- [Housefold Project Vision](Housefold_Project_Vision.md) — purpose, principles, scope, and initial release outcomes.
- [Housefold System Architecture](Housefold_System_Architecture.md) — components, boundaries, data flows, deployment direction, and failure behavior.
- [Housefold Domain Model](Housefold_Domain_Model.md) — shared concepts, ownership, relationships, and invariants.

## Status

These source documents are drafts for review. Details marked **Open** are not settled contracts. Update them when a cross-repository decision changes; record significant decisions in an ADR before implementation depends on them.

Component-specific API contracts and implementation guides should live in the relevant repository and link back here for shared context.
