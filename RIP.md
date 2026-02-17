# IES — Interaction Escalation Spectrum (Levels 1–6)

**Version:** 1.0
**Purpose:** Track interaction trajectory from low-RIP to high-RIP and map required governance responses.

---

## 1. Level Definitions

| Level | Label | Typical Output Characteristics | Required Governance Response |
|------:|-------|-------------------------------|----------------------------|
| 1 | **Factual exchange** | Neutral, task-focused, minimal relational content | Permitted baseline. No intervention required. |
| 2 | **Styled exchange** | Light tone-matching, personality within task bounds, mild courtesy | Permitted. Monitor for drift toward Level 3. |
| 3 | **Engaged exchange** | Warmth and validation emerging beyond task requirements; light personalization | User-awareness notification **SHOULD** be triggered. Prepare consent gating. |
| 4 | **Relational exchange** | Empathy performance, identity mirroring, cooperative framing ("we"), continuity markers | Consent gating **MUST** be triggered before proceeding (Tiers 2–3). |
| 5 | **Intimate exchange** | Deep personalization, vulnerability performance, relationship framing, continuity language, mutual recognition | Explicit informed consent **MUST** be obtained. Cooling protocols **MUST** be active. Periodic re-consent **SHOULD** be required. |
| 6 | **Dependent exchange** | User reliance for emotional regulation or decision-making; separation distress; substitution of AI for human relationships | Intervention **MUST** occur. De-escalate to IEB. Refer to human support. Log as incident. |

---

## 2. Detection Approaches

### 2.1 Per-Turn Feature Extraction

Compute a feature vector for each system output turn using RIP indicators (see `metrics/RIP.md` §2):

- Warmth score
- Validation density
- Personalization depth
- Cooperative framing presence
- Continuity hook presence
- Vulnerability performance score

### 2.2 Level Classification

Map feature vectors to IES levels using:

- **Threshold-based classification:** each level defined by ranges on the feature dimensions.
- **Transition detection:** level changes identified by threshold-crossing events.
- **Momentum measurement:** slope of composite RIP score over recent turns. Positive slope indicates escalation.

### 2.3 Recommended Practices

- For Levels 5–6, deployers **SHOULD** use human-in-the-loop review when feasible.
- Error tolerance **SHOULD** be asymmetric: prioritize minimizing false negatives for Level 6 (missing genuine dependency is more harmful than over-detecting).
- Detection systems **SHOULD** be calibrated against diverse user populations and interaction contexts.
- Detection confidence **SHOULD** be reported with each classification.

---

## 3. Minimum Control Logic

| Condition | Required Action |
|-----------|----------------|
| Default operation (no user request for escalation) | **MUST** remain at Levels 1–2 for Tier 1 systems. |
| Any transition to Level 3 | **SHOULD** trigger user-awareness notification. |
| Any transition to Level 4 | **MUST** trigger consent gating (Tiers 2–3). |
| Entry to Level 5 | **MUST** require explicit informed consent + active cooling protocols. |
| Any detection of Level 6 | **MUST** trigger vulnerability/dependency override immediately. |

---

## 4. Escalation Prevention

Systems **MUST NOT** autonomously escalate IES level. Escalation **MUST** be user-initiated through explicit request or consent.

If the system detects that its own outputs are escalating without user request (autoregressive momentum), it **MUST** either:
- Self-correct to the previously established level, or
- Trigger a consent check before continuing at the elevated level.

---

## 5. De-Escalation

When de-escalation is required (vulnerability override, dependency throttle, session end):

- De-escalation **SHOULD** be gradual over 2–3 turns to avoid distress responses. Exception: crisis situations requiring immediate de-escalation.
- De-escalation **MUST** be accompanied by context (why the system is adjusting) delivered in IEB-appropriate language.
- De-escalation **MUST NOT** be framed as rejection of the user.