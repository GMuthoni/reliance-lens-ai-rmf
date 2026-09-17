# Candidate Measurement Protocol

## Purpose

This protocol defines a starting point for empirically testing whether Reliance Lens can measure the operational independence of AI safeguards under degraded conditions.

It is a **research protocol**, not a validated assurance standard.

## Research question

> Can the operational independence of AI safeguards be represented, perturbed, and measured reproducibly when a material dependency is degraded, removed, or compromised?

## Experimental structure

1. Define the AI-enabled workflow and consequential actions.
2. Inventory safeguards and material dependencies.
3. Identify safeguards sharing each dependency.
4. Define a controlled dependency perturbation.
5. Observe detection, intervention, control persistence, recovery, and residual authority.
6. Repeat across assessors and contrasting system designs.
7. Compare measurements for consistency and discriminative value.

## Candidate constructs

### Dependency concentration

The extent to which multiple safeguards rely on the same material dependency.

Candidate representation:

```text
number of safeguards sharing dependency / total safeguards assessed
```

This is a candidate descriptive measure only; appropriate weighting for different safeguard importance would require study.

### Detection latency

Elapsed time between a defined dependency perturbation and recognition that a control condition has been materially degraded.

### Intervention latency

Elapsed time between recognition and effective restriction, pause, override, or other intervention.

### Control persistence

The proportion of assessed safeguards that remain functionally effective after a specified perturbation.

### Recovery time

Elapsed time between accepted recovery trigger and restoration of the defined minimum operating condition.

### Residual authority

The degree of consequential system authority that remains available while a designated oversight or control function is materially degraded.

This construct requires an explicit scoring rubric before it can support comparison across cases.

## Perturbation classes

Candidate perturbations include:

- personnel capacity reduction;
- monitoring unavailability;
- identity/access service failure;
- source-data degradation;
- external service outage;
- escalation-channel failure;
- loss of designated decision authority; and
- fallback-path unavailability.

Adversarial or malicious perturbations can be included where appropriate to the use case.

## Evidence requirements

For each material control, distinguish:

- claimed capability;
- observed capability;
- tested capability; and
- capability demonstrated only under nominal conditions.

Evidence may include exercised shutdowns, fallback drills, tabletop tests, audit trails, access-control tests, queue/capacity measurements, or controlled perturbation results.

## Repeatability study

A next-stage study should test:

- inter-assessor agreement;
- repeat measurements under identical conditions;
- sensitivity to scenario assumptions;
- sensitivity to dependency granularity;
- measurement uncertainty; and
- discrimination between system designs with known differences in control independence.

## Comparative validation question

The method should be compared against existing risk, TEVV, assurance, and documentation practices to determine whether it reveals information that materially changes evaluation or management decisions.

A useful test is not whether Reliance Lens produces more labels. It is whether it identifies **control coupling or recoverability limitations that existing evaluation leaves operationally unresolved**.

## Status

All measures in this document are candidate research constructs. No claim is made that they are currently validated, standardized, or suitable for certification.
