# Housefold Project Vision

**Status:** Initial baseline; several implementation decisions remain open.

## Purpose

Housefold is a local-first home computing platform that extends Home Assistant with a dependable runtime, clearer system boundaries, and room for richer automation, presence, interaction, diagnostics, and intelligence capabilities.

The house should remain useful when the internet, a remote server, or an optional AI service is unavailable. When Housefold acts or reaches a conclusion, it should be possible to understand what it observed, why it decided, what it changed, and what happened afterward.

## Product shape

- **Home Assistant** remains the established home-automation foundation for device integrations, entity state, services, and the physical-device ecosystem.
- **Housefold Runtime** is the stable local supervisor and platform boundary. It owns lifecycle, module management, health and recovery, and the canonical Housefold API.
- **Housefold Bridge** is a deliberately thin Home Assistant integration. It exposes the HA capabilities the runtime needs and translates between HA's model and the runtime contract.
- **Housefold modules** add capabilities such as automations, presence, interactions, diagnostics, and intelligence. These are architectural modules; they do not each need a repository or process from the outset.
- **Housefold UI** is an optional full-featured PWA. The runtime retains a small management and recovery interface so basic setup and recovery do not depend on the PWA.

## Principles

### Local operation first

Latency-sensitive and safety-relevant household behavior should run locally. A VPS, internet connection, cloud service, or AI model must not be a required step in the critical path for basic local operation.

### Clear ownership and boundaries

Home Assistant owns its device ecosystem and HA-native state. Housefold owns its runtime contract and the Housefold-specific interpretations, decisions, module lifecycle, and diagnostics it creates. The Bridge adapts between these worlds; it does not become the place for platform policy or automation logic.

### Explainable behavior

Housefold should preserve enough structured context to explain important behavior: observations, inferences, decisions, commands, and outcomes. Agents and people should be able to inspect the same evidence and distinguish recorded facts from inferred state.

### Privacy by design

Household identity and activity are sensitive. Keep data local by default, expose only what a capability needs, and apply an explicit privacy boundary before household data reaches remote or AI services. Do not treat raw logs as an agent API.

### Optional intelligence, deterministic operation

Learning and AI can analyze, explain, and propose improvements. They should not silently replace deterministic behavior or become mandatory for basic operation. Any future ability to apply consequential changes needs an explicit authorization and verification boundary.

### Incremental, stable contracts

Start with a small number of independently maintained products: runtime, bridge, and UI. Keep the runtime contract deliberately stable and let other capabilities evolve behind documented interfaces. Add repositories only when independent versioning or deployment justifies them.

## Initial usable release

An initial release should demonstrate that:

1. The Runtime runs locally alongside Home Assistant and supervises its own lifecycle.
2. The Bridge can deliver the required HA state and event information to the Runtime and route supported requests back to HA.
3. At least one Housefold capability can consume the Runtime contract without depending directly on HA internals.
4. A local household function continues through loss of internet or VPS connectivity.
5. The system reports health and can explain a representative action from its available evidence.
6. The optional UI can be absent without preventing core local operation.

The precise first feature, installation path, protocol schema, and acceptance measurements remain **Open** until their focused specifications are written.

## Out of scope for the foundation

- Replacing Home Assistant's entire integration ecosystem.
- Splitting every architectural module into its own repository or microservice.
- Making cloud AI a prerequisite for ordinary household automation.
- Allowing an agent to make unreviewed, unrestricted changes to the household.
- Promising stable external APIs before the Runtime and Bridge contracts are versioned.

## Open questions

- What is the minimum capability set for the first usable release?
- Which runtime functions are in the first release versus later modules?
- What install and update experience is appropriate for the Home Assistant environment?
- What authentication and authorization model protects local and remote control surfaces?
- What household data, if any, may leave the local environment, and under which explicit policy?
