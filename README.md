# Reliance Lens × NIST AI RMF
## Testing safeguard independence under degraded conditions

**Status:** Analytical prototype / worked application  
**Version:** 0.1

This repository presents a worked analytical application of **Reliance Lens** to the NIST AI Risk Management Framework (AI RMF).

Reliance Lens examines whether safeguards around an AI-enabled system remain operationally effective when people, systems, data, authority, or other material dependencies are degraded, unavailable, or compromised.

It is designed to **complement—not replace—the NIST AI RMF**.

## Core proposition

AI risk assessments commonly document safeguards such as human review, model monitoring, appeals, manual fallback, incident response, and escalation procedures.

Reliance Lens asks an additional operational question:

> **Do these safeguards remain effective when a shared dependency is degraded?**

A system may have several formally separate controls while relying on the same personnel, workflow, data, infrastructure, decision-maker, or communications channel. A single dependency failure can therefore disable several safeguards together.

The central analytical chain is:

```text
Shared dependency
→ simultaneous safeguard degradation
→ possible practical-authority shift
→ loss of meaningful oversight
→ intervention / recovery problem
```

## What Reliance Lens adds

### 1. Dependency-first analysis

The unit of analysis is not only the model or control. It is the relationship among:

```text
AI function
→ safeguard
→ required dependency
→ degraded condition
→ practical consequence
```

### 2. Control-coupling analysis

The method identifies whether multiple safeguards depend on the same resource or capability.

Example:

```text
Recruiter capacity
├── human review
├── manual fallback
├── candidate correction
└── ranking suspension
```

A single capacity failure may therefore affect oversight, fallback, recourse, and intervention simultaneously.

### 3. Formal versus practical authority

An AI system may formally be advisory while practically determining:

- which cases are seen first;
- which cases receive meaningful review;
- which cases are delayed; or
- which people can realistically reach a human decision-maker.

Reliance Lens records this possible transfer of **practical authority without a formal transfer of authority**.

### 4. Stress-based testing

The method converts governance claims into operational tests.

Instead of asking:

> Is human oversight present?

it asks:

> **What happens when the human oversight function is unavailable, overloaded, delayed, or unable to change the result?**

## Candidate measurement constructs

This repository proposes candidate measurements for future validation. They are **not validated metrics**.

| Construct | Candidate measure | Example observation |
|---|---|---|
| Dependency concentration | proportion of safeguards sharing a material dependency | 4 of 6 safeguards depend on recruiter capacity |
| Detection latency | time from dependency degradation to recognized control failure | minutes / hours |
| Intervention latency | time from recognized failure to effective restriction, pause, or override | minutes / hours |
| Control persistence | proportion of safeguards remaining effective after a defined perturbation | 2 of 5 controls remain effective |
| Recovery time | time to restore meaningful control / review | hours / days |
| Residual authority | consequential system authority retained while oversight is degraded | qualitative or ordinal score |

The purpose of these constructs is to make the research question testable. Their validity, repeatability, uncertainty, and discriminative value require empirical testing.

## NIST AI RMF relationship

Reliance Lens is a complementary assessment aid for the four AI RMF Functions:

| AI RMF Function | Reliance Lens contribution |
|---|---|
| GOVERN | Assign ownership for dependencies, escalation, intervention, recovery, and learning |
| MAP | Map the AI-enabled workflow, safeguards, dependencies, affected parties, and authority relationships |
| MEASURE | Test whether safeguards remain available and effective under degraded conditions |
| MANAGE | Prioritize interventions that reduce control coupling and preserve usable recovery paths |

The artifact does **not** claim to create a new NIST function, control family, certification, or NIST-approved method.

## Worked example

The included case concerns an AI ranking system used to prioritize job applications for recruiter review.

The system is not formally the hiring decision-maker. However, it may determine which applications receive attention first and which candidates are practically visible to recruiters.

The worked scenario tests:

```text
Recruiter review capacity becomes unavailable or severely constrained
while the ranking system remains technically available.
```

The analysis asks:

1. Does the organization detect the loss of meaningful review?
2. Does ranking continue?
3. Does ranking acquire greater practical authority?
4. Does manual fallback remain independent?
5. Can candidates still obtain correction or recourse?
6. Can ranking be suspended by an authorized person?
7. Is the event recorded as an oversight-control failure?
8. Can normal operation be restored and explained?

## Main analytical finding

The worked case identifies a possible coupling pattern:

```text
Recruiter capacity failure
→ human review degraded
→ manual fallback degraded
→ correction delayed
→ ranking authority increases
→ authority transfer may remain undetected
```

The material risk is therefore not only model error. It is the possibility that several safeguards fail together because they rely on the same operational dependency.

## Evidence discipline

The repository separates:

- documented facts;
- analytical inferences;
- hypotheses;
- testable claims; and
- claims not established by the artifact.

The employment-screening case is an **analytical fixture**, not a documented incident.

This repository does not claim that Reliance Lens:

- has been validated;
- improves AI RMF outcomes;
- is reproducible between assessors;
- is superior to existing AI governance or assurance methods; or
- constitutes a NIST-approved framework.

## Intended use

This artifact can be used as:

- a worked AI RMF use case;
- a tabletop exercise;
- a control-dependency worksheet;
- a governance review aid;
- a basis for expert critique; and
- a starting point for empirical validation.

## Repository structure

```text
reliance-lens-ai-rmf/
├── README.md
├── LICENSE
├── CITATION.cff
├── docs/
│   ├── worked-example-employment-screening.md
│   ├── ai-rmf-crosswalk.md
│   ├── measurement-protocol.md
│   └── evidence-boundary.md
├── artifacts/
│   ├── reliance-lens-worksheet.md
│   ├── employment-screening-dependency-map.mmd
│   └── employment-screening-assessment.json
└── schemas/
    └── reliance-lens-assessment.schema.json
```

## Related research

- https://lens.nieleze.com/
- https://pulse.nieleze.com/
- https://www.nieleze.com/
- https://underlying.work/

## NIST reference

The repository is intended as an independent research artifact and is not affiliated with or endorsed by NIST.

NIST AI Consortium:  
https://www.nist.gov/artificial-intelligence/nist-ai-consortium

NIST AI RMF:  
https://www.nist.gov/itl/ai-risk-management-framework

## License

Apache License 2.0. See `LICENSE`.
