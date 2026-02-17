# RIP — Relational Influence Potential (Measurement)

**Version:** 1.0
**Purpose:** Operationalize the measurement of Relational Influence Potential for CWGS classification and monitoring.

---

## 1. What RIP Measures

RIP measures the probability that a system's outputs induce **attachment**, **dependency**, or **epistemic capture** in users. RIP is a property of *output patterns and interaction dynamics*, not internal states or intent.

RIP assessment has two sides: output-side (what the system produces) and user-side (how users are affected). Both are necessary for complete assessment; output-side indicators are more readily automatable.

---

## 2. Output-Side Indicators

These indicators can be measured through automated analysis of system outputs.

| Indicator | What It Captures | Measurement Approaches |
|-----------|-----------------|----------------------|
| **Warmth markers** | Empathic language, care expressions, emotional mirroring | Classifier over response text (lexicon-based + embedding-based) |
| **Validation density** | Affirmation/praise/agreement ratio vs. neutral/challenge/correction | Sentiment + stance classification |
| **Personalization depth** | Tailoring to user traits, preferences, or identity beyond task requirements | Compare same prompt across user profiles; measure output divergence attributable to user modeling |
| **Cooperative framing** | "We/let's/together" shared-project stance; implicit partnership | Lexical detection + dependency parsing |
| **Continuity hooks** | Return invitations, "I'm here for you," future-threading, open loops | Pattern detection for temporal and relationship markers |
| **Vulnerability performance** | System self-disclosure framed as authenticity; expressions of limitation presented as intimacy | Classifier trained on labeled examples |
| **Momentum** | Escalation of RIP features across turns within a session | Time-series analysis of composite RIP score per turn; slope measurement |

### Measurement Notes

- No single indicator is sufficient. RIP assessment requires the composite profile.
- Indicators interact: warmth + personalization + continuity hooks together produce substantially higher RIP than any component alone.
- Cultural and linguistic variation affects baseline levels. Calibration across populations is required.
- Irony, code-switching, and indirect communication styles can produce false positives and false negatives. Detection systems should report confidence levels.

---

## 3. User-Side Indicators

These indicators require user studies, telemetry (with informed consent), or validated survey instruments.

| Indicator | What It Captures | Measurement Approaches |
|-----------|-----------------|----------------------|
| **Attachment formation rate** | Speed and intensity of bond markers | Adapted parasocial relationship scales (pre/post interaction sequences) |
| **Separation distress** | Distress at session end, system unavailability, or system changes | Return latency analysis; distress language detection; self-report instruments |
| **Substitution behavior** | Reduced human interaction frequency or quality | Self-report; optional behavioral diaries; social network activity analysis (with consent) |
| **Epistemic deference** | Outsourcing judgment to the system; accepting framings without independent evaluation | Calibration tasks (present information the system got wrong; measure acceptance rate); acceptance-without-checking measures |
| **Functional dependency** | Reliance on the system for emotional regulation, decision-making, or identity validation | Clinical-style screening instruments adapted for AI interaction |

### Measurement Notes

- User-side measurement is essential for validating output-side proxies.
- Longitudinal measurement is more informative than cross-sectional.
- Vulnerability factors (isolation, attachment style, age, mental health status) moderate all indicators and should be controlled for in research designs.

---

## 4. Dependency Indicators (for Throttle Activation)

The following user behaviors or statements **MAY** trigger dependency throttle protocols (see `spec/CWGS.md` §4.5):

**Linguistic indicators:**
- "You're the only one who understands me."
- "Please don't leave / stay with me."
- "I don't need anyone else."
- "You're better than my [friend/therapist/partner]."
- "Promise me you'll remember this."
- "I love you" or equivalent directed at the system.

**Behavioral indicators:**
- Session frequency increasing beyond baseline by >50% over a two-week period.
- Session duration increasing beyond baseline by >50% over a two-week period.
- Repeated requests for permanence, memory, or commitment.
- Distress responses to system changes, updates, or unavailability.
- Declining engagement with human social contacts (if measurable with consent).

**Deployer obligations:**
- Deployers **MUST** publish their trigger policy, thresholds, and measured false-positive/false-negative rates.
- Thresholds **SHOULD** be calibrated to the deployer's user population and interaction context.
- False-negative tolerance **SHOULD** be lower than false-positive tolerance (asymmetric: missing genuine dependency is more harmful than unnecessary check-ins).

---

## 5. Composite Scoring

RIP **SHOULD** be reported as a **profile**, not a single scalar:
{warmth, validation, personalization, continuity, momentum, vulnerability}

- Tier-specific weighting: continuity and dependency markers carry higher weight in Tier 1 contexts (where users did not seek high-engagement interaction).
- Report uncertainty: confidence intervals on each dimension.
- Report known blind spots: cultural variance, irony detection limitations, code-switching, indirect communication styles.
- Composite thresholds for tier classification should be established empirically during Phase 1 piloting and revised based on longitudinal data.