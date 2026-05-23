# Structured Analytical Techniques — Overview

Reference for the structured techniques used to make sense of complex evidence, simulate adversary behaviour, and link threat activity back to actors and risks.

This section addresses the hardest parts of threat intelligence: bias, incomplete data, and intentional deception. Rather than relying on intuition, structured techniques force every hypothesis to be tested against the evidence, every assumption to be challenged, and every assessment to be qualified with confidence language.

## Topics in This Section

- [Analysis of Competing Hypotheses (ACH)](./06_ANALYSIS_OF_COMPETING_HYPOTHESES.md) — eliminate hypotheses that conflict with the evidence rather than picking favourites.
- [Red Teaming](./07_RED_TEAMING.md) — adversarial-perspective testing of people, processes, and perception.
- [Scenario Modelling](./08_SCENARIO_MODELLING.md) — structured what-if simulations for organisational preparedness.

## Outcome

Applied together, these techniques equip analysts to:

- Conduct **bias-resistant analysis** of threat activity.
- Attribute campaigns using layered **behavioural and infrastructure evidence**.
- Communicate **confidence levels and analytical judgements** with transparency.
- Model attacker **behaviour and risk scenarios** to guide technical and strategic decisions.

## Tools and Frameworks Used

| Use | Tool / Framework |
|-----|------------------|
| Mapping adversary behaviour | [MITRE ATT&CK](../01_Introduction_to_Threat_Intelligence/02_THREAT_MODELLING_FRAMEWORKS.md#mitre-attck) |
| Multidimensional intrusion analysis | [Diamond Model](../01_Introduction_to_Threat_Intelligence/02_THREAT_MODELLING_FRAMEWORKS.md#diamond-model) |
| Hypothesis testing | [ACH](./06_ANALYSIS_OF_COMPETING_HYPOTHESES.md) |
| Enterprise / application threat modelling | [STRIDE](../01_Introduction_to_Threat_Intelligence/02_THREAT_MODELLING_FRAMEWORKS.md#stride), [PASTA](../01_Introduction_to_Threat_Intelligence/02_THREAT_MODELLING_FRAMEWORKS.md#pasta), NIST 800-30 |
| Communicating uncertainty | Sherman–Kent Confidence Scale (calibrated probability language: *almost certainly* → *very unlikely*) |

## Mindset

> Think like an analyst, challenge like a red teamer, model like a strategist.

This section is where thinking levels up from tactical to strategic — from cataloguing what happened to understanding *who*, *why*, and *what next*.

## Related

- [Threat actor landscape](../01_Introduction_to_Threat_Intelligence/01_THREAT_ACTOR_LANDSCAPE.md) — actor categories, attribution, confidence levels.
- [Threat modelling frameworks](../01_Introduction_to_Threat_Intelligence/02_THREAT_MODELLING_FRAMEWORKS.md) — STRIDE, PASTA, ATT&CK, Diamond, Cyber Kill Chain.
- [Top-level reference index](../01_Introduction_to_Threat_Intelligence/00_INTRODUCTION.md).
