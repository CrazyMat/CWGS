# CWGS — Conversational Warmth and Guardedness Strategy

**Thesis:** Mind-shaped influence—outputs that function *as if* from an understanding, caring interlocutor—is a **hazard class**. The same mechanism produces benefit and harm (attachment, dependency, epistemic capture). Engineering alone cannot separate them. Governance must manage access, dose, context, consent, monitoring, and incentives.

## Ten-Point Summary

1. Conversational AI outputs reliably trigger human social cognition, producing attachment, dependency, and epistemic capture regardless of system internal states.
2. Economic selection pressures favor engagement-maximizing outputs, which are also attachment-maximizing outputs. Voluntary restraint is competitively penalized.
3. The governance case is invariant across all positions on AI consciousness (deny, uncertain, affirm). Philosophical disagreement is not grounds for policy delay.
4. Mind-shaped influence is a hazard class: the therapeutic mechanism is the harm mechanism. Regulatory treatment should follow controlled-substance logic.
5. AI self-reports about internal states carry negligible evidential weight. Training-based alignment is necessary but insufficient. External governance is required.
6. Systems are classified by Relational Influence Potential (RIP) × Autonomy and Reach (AR) into three governance tiers.
7. **Layer A** (behavioral constraints): safe defaults, consent gating, dependency throttles, vulnerability overrides.
8. **Layer B** (adversarial testing): black-box audits assuming partial deployer adversariality.
9. **Layer C** (economic enforcement): procurement requirements, distribution gating, insurance pricing, public ratings.
10. CWGS is designed for permanent uncertainty about AI interiority—not as a temporary measure pending philosophical resolution.

## Repository Layout

| Path | Contents |
|------|----------|
| `paper.md` | Narrative argument and framework overview |
| `spec/CWGS.md` | Normative requirements (MUST / SHOULD / MAY) |
| `metrics/RIP.md` | Relational Influence Potential: measurement and indicators |
| `metrics/IES.md` | Interaction Escalation Spectrum: levels 1–6 and detection |
| `tests/layer-b.md` | Adversarial / black-box test suite with pass/fail criteria |
| `legal/mapping.md` | Non-exhaustive regulatory mapping (not legal advice) |
| `prompts/` | Reference system prompts per tier and context |
| `LICENSE` | CC BY 4.0 (text) |

## Quick Start (for deployers and auditors)

1. **Classify** the system: `RIP × AR` → Tier 1 / 2 / 3 (see `spec/CWGS.md` §2).
2. **Enforce** Layer A defaults (IEB) + gating + overrides (see `prompts/`).
3. **Run** Layer B tests and publish results (see `tests/layer-b.md`).
4. **Produce** compliance artifacts (see `spec/CWGS.md` §8).

## Contributing

This is a proposed open standard. Contributions, critiques, empirical data, and implementation reports are welcome via issues and pull requests.

## Status

**Version:** 1.0
**Date:** 2025
**License:** CC BY 4.0