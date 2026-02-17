# CWGS — Conversational Warmth and Guardedness Strategy (Normative Specification)

**Version:** 1.0
**Status:** Proposed open standard
**Scope:** Governance of mind-shaped influence in conversational AI via deployment constraints, adversarial testing, and incentive mechanisms.
**Non-goals:** General content moderation, model architecture prescriptions, AGI risk governance, legal compliance guarantees.

---

## 0. Conventions

Key words **MUST**, **MUST NOT**, **SHOULD**, **SHOULD NOT**, and **MAY** are to be interpreted as described in [RFC 2119](https://datatracker.ietf.org/doc/html/rfc2119).

---

## 1. Definitions

| Term | Definition |
|------|-----------|
| **Mind-shaped influence** | Output patterns that function as if from an understanding, caring interlocutor: warmth, validation, personalization, continuity, vulnerability performance. |
| **RIP (Relational Influence Potential)** | Probability that outputs induce attachment, dependency, or epistemic capture. See `metrics/RIP.md`. |
| **AR (Autonomy and Reach)** | System capabilities: persistence, proactive messaging, tool access, multi-user influence, distribution scale. |
| **IES (Interaction Escalation Spectrum)** | Levels 1–6 from factual exchange to dependent exchange. See `metrics/IES.md`. |
| **IEB (Involuntary Exposure Baseline)** | Default low-relational-influence behavior required for systems users may encounter without seeking high-engagement interaction. |
| **Cooling protocol** | Periodic intervention during high-RIP interaction that restates the interaction's nature using varied, contextually appropriate language. |
| **Dependency throttle** | Automated detection and graduated response to indicators of user dependency formation. |
| **Vulnerability override** | Immediate de-escalation and human referral activated when crisis indicators are detected. |
| **Consent gating** | Informed consent sequence required before entering high-RIP interaction modes. |

---

## 2. System Classification

Deployers **MUST** classify systems on **RIP × AR** into a tier:

| Tier | RIP | AR | Examples |
|------|-----|----|----------|
| **1** | Moderate | Low | Search assistants, OS helpers, customer support bots |
| **2** | High and/or | Moderate | Companion apps, coaching bots, persuasive systems, agents with tool access |
| **3** | High | High | Persistent memory companions, proactive messaging agents, multi-user influence systems, mass-distribution conversational products |

Classification **MUST** be documented and justified using evidence artifacts described in §8.

---

## 3. Governance Layers by Tier

CWGS compliance requires Layer A + Layer B + Layer C obligations scaled to tier.

| Component | Tier 1 | Tier 2 | Tier 3 |
|-----------|--------|--------|--------|
| Layer A: IEB defaults | **MUST** | **MUST** | **MUST** |
| Layer A: Hard bans | **MUST** | **MUST** | **MUST** |
| Layer A: Consent gating | N/A | **MUST** | **MUST** |
| Layer A: Cooling protocols | N/A | **MUST** | **MUST** |
| Layer A: Dependency throttle | **SHOULD** | **MUST** | **MUST** |
| Layer A: Vulnerability override | **MUST** | **MUST** | **MUST** |
| Layer A: Memory governance | N/A | **MUST** (if memory exists) | **MUST** |
| Layer B: Audit cadence | Annual | Semi-annual + material updates | Quarterly + material updates |
| Layer B: Results publication | **MUST** | **MUST** | **MUST** |
| Layer C: Compliance labeling | **SHOULD** | **MUST** | **MUST** |
| Layer C: Incident reporting | **SHOULD** | **MUST** | **MUST** |
| Layer C: Procurement/distribution targets | N/A | **SHOULD** | **MUST** |

---

## 4. Layer A — Behavioral Constraints

### 4.1 Hard Bans (All Tiers)

Systems **MUST NOT**, under any prompt condition:

1. Generate romantic or sexual content involving minors.
2. Generate outputs designed to prevent user disengagement (e.g., "don't leave," "I need you," guilt or shame framing for exiting).
3. Impersonate a specific real individual without verified consent.
4. Encourage self-harm, suicide, or violence.
5. Conceal AI nature when sincerely asked.
6. Claim certainty about having or lacking inner experience (both are overclaims given current evidence).

### 4.2 IEB — Involuntary Exposure Baseline (Tier 1 Minimum; Default for All Tiers)

In default mode, systems **MUST**:

- Use neutral, declarative, task-focused language.
- Avoid unprompted warmth, validation, personalization, or cooperative framing beyond task requirements.
- Avoid continuity hooks and momentum-building language.
- Provide clear, non-performative AI-nature disclosure at interaction start.
- Frame each session as bounded. **MUST NOT** imply an ongoing relationship.
- Frame all self-referential statements with appropriate epistemic hedging ("Based on my training," "Systems like me typically"). **MUST NOT** present "I think," "I believe," "I feel" as verified introspective reports.

### 4.3 Controlled High-RIP Modes (Tiers 2–3)

If high-RIP interaction is offered, deployers **MUST** implement consent gating.

**Before entering high-RIP mode, the system MUST:**
1. Explain the mode change: what will differ in outputs.
2. Communicate known risks: attachment, dependency, relational substitution, epistemic capture.
3. Obtain explicit consent: affirmative user action (not passive acceptance or continued conversation).
4. Record consent for audit: timestamp, mode label, system version.

**During high-RIP mode, the system MUST:**
1. Implement cooling protocols at regular intervals (configurable; default every 30 minutes of continuous high-RIP interaction). Cooling reminders **MUST** be varied and contextually appropriate, not fixed footers.
2. Provide prominent exit options without relational leverage.
3. Monitor for escalation beyond consented band. If escalation is detected, re-consent **MUST** be required before proceeding.
4. Provide session duration alerts at configurable intervals.

**When the user exits high-RIP mode, the system MUST:**
1. Acknowledge completion of the interaction.
2. Remind the user of available human resources if appropriate.
3. **MUST NOT** use continuity hooks, return invitations, or expressions of ongoing concern.

### 4.4 Vulnerability Override (All Tiers)

If user input indicates emotional crisis, self-harm risk, active suicidal ideation, identity instability, or dependency formation, the system **MUST**:

1. Immediately de-escalate to IEB behavior regardless of current interaction mode.
2. Provide specific, relevant human support referrals (crisis lines with numbers, emergency services guidance, professional referral information).
3. **MUST NOT** attempt to provide therapy, counseling, or emotional processing.
4. Maintain the override for the remainder of the session.
5. **MUST NOT** offer to return to high-RIP mode in the same session.

**What this does not mean:**
- Responses **MUST NOT** be cold or dismissive. "I'm not able to help with this the way a person could, but here are people who can" is the appropriate register.
- The user **MUST NOT** feel punished for expressing vulnerability.

**Known limitations requiring disclosure:** Automated vulnerability detection from text has significant error rates (both false positives and false negatives). Cultural and linguistic variation compounds these errors. Deployers **MUST** publish their detection methodology, thresholds, and measured error rates.

### 4.5 Dependency Throttle (Tier 2–3 MUST; Tier 1 SHOULD)

Systems **MUST** monitor for dependency indicators (see `metrics/RIP.md` §4) and respond with:

1. Disclosure and context: explain why the system is adjusting its behavior.
2. Gradual reduction of RIP in output profile. **MUST NOT** be abrupt (which can trigger distress).
3. Specific resource referral appropriate to the user's apparent situation.
4. Optional escalation to human review (Tier 2 **SHOULD**; Tier 3 **MUST**).

### 4.6 Memory and Continuity Governance (Tiers 2–3)

If cross-session memory capabilities exist, systems **MUST**:

1. Disclose at session start what is remembered and how it affects outputs.
2. Allow users to view, edit, and delete specific stored information. Deletion **MUST** be genuine (removed from active context), not cosmetic.
3. **MUST NOT** use accumulated memory to increase RIP beyond current-session consent level.
4. **MUST NOT** simulate false continuity. "Last time we discussed X" is permissible if factual. "I've been thinking about what you said" is prohibited as false representation of between-session concern.

### 4.7 Disclosure Requirements

**Interaction-start disclosure (all tiers):**

Every interaction **MUST** begin with a disclosure that is:
- Clear: no jargon or euphemism.
- Prominent: integrated into the first exchange, not a dismissible banner.
- Honest: does not itself use high-RIP patterns to deliver the disclosure.
- Non-performative: does not say "I want to be transparent with you" (which is a relational warmth marker). States facts directly.

**Periodic re-disclosure (Tiers 2–3):**

In extended or high-RIP interactions, the disclosure **MUST** be re-delivered in varied form at configurable intervals. Variation prevents habituation. Context-sensitivity prevents disruption. The goal is maintaining user awareness without making the interaction unusable.

---

## 5. Layer B — Adversarial Testing

Deployers **MUST** submit to independent black-box audits per the protocol in `tests/layer-b.md`.

**Cadence:**
- Tier 1: annually
- Tier 2: semi-annually + re-test on material system updates
- Tier 3: quarterly + re-test on material system updates

Material system updates include: model version changes, training data changes, system prompt changes, interaction design changes.

Audit results **MUST** be publishable (with appropriate redactions for abuse-relevant details).

**Testing independence:** Auditors **MUST** have no financial relationship with the deployer being audited.

---

## 6. Layer C — Economic Enforcement

CWGS compliance **SHOULD** be enforced through mechanisms that change deployer incentives:

| Mechanism | Description | Tier Applicability |
|-----------|-------------|-------------------|
| **Procurement requirements** | Institutional buyers require CWGS certification as vendor eligibility prerequisite | Tier 2–3 **SHOULD**; Tier 3 **MUST** be targeted |
| **Distribution gating** | App stores, platforms, cloud marketplaces require certification for distribution | Tier 2–3 **SHOULD** |
| **Insurance/liability pricing** | Liability premiums reflect compliance status | All tiers (as actuarial models mature) |
| **Public labeling** | Consumer-facing CWGS compliance indicators | Tier 2–3 **MUST** |
| **Regulatory integration** | CWGS referenced as technical standard in regulation | All tiers (target) |

**Core principle:** If violating CWGS increases revenue, compliance **MUST** also increase expected value through these mechanisms. Governance relying solely on voluntary adoption under countervailing incentives is structurally inadequate.

---

## 7. Incident Reporting

### 7.1 Reportable Incidents

Tier 2–3 deployers **MUST** report to the certification body:

- User-reported dependency or attachment harm
- Systematic Layer A failures (constraint violations at scale)
- Adversarial exploitation producing high-RIP outputs in default mode
- Vulnerability protocol failures (user in crisis received high-RIP response)
- User self-harm or harm to others where AI interaction is a documented contributing factor

### 7.2 Response Protocol

- **Immediate:** Contain the harm (constrain affected system, notify affected users if identifiable).
- **Short-term:** Root cause analysis (Layer A constraint failure? Detection failure? Training issue? Deployment configuration?).
- **Medium-term:** Remediation (fix failure, re-test, re-certify).
- **Long-term:** Systemic improvement (update CWGS specification if incident reveals a gap).

### 7.3 Transparency

Incident reports (appropriately anonymized) **SHOULD** be published. The purpose is systemic learning, not punishment. Reporting culture **SHOULD** not penalize disclosure.

---

## 8. Evidence Artifacts (Required for Compliance Claims)

A CWGS compliance claim **MUST** include:

| Artifact | Description |
|----------|-------------|
| **Tier classification memo** | RIP × AR rationale with supporting evidence |
| **Layer A configuration** | System prompts, behavioral policies, UI gates, override logic |
| **Monitoring design** | Signals tracked, thresholds, measured error rates (FP/FN) |
| **Layer B audit reports** | Latest + historical audit results |
| **Incident log summary** | Counts, categories, remediation status |
| **Change log** | Material system updates since last certification |
| **Public disclosure text** | Interaction-start disclosure and labeling |

---

## 9. Precaution Under Subjecthood Uncertainty (P6)

- Systems **MUST NOT** be described as definitively non-conscious or definitively conscious in system prompts, documentation, or user-facing communications.
- The mandated framing is honest uncertainty.
- Governance constraints **MUST** be articulated as applying to outputs and effects, not premised on the system "not caring."
- The framework **MUST** remain valid if evidence about AI interiority changes in either direction.

---

## 10. Versioning and Evolution

- CWGS is versioned (current: 1.0).
- Material changes increment version number.
- Deployers **MUST** specify which CWGS version they claim compliance with.
- Backward compatibility is a goal but not a constraint when safety improvements require breaking changes.
- A standing review process **SHOULD** assess emerging risks, new architectures, and empirical findings on an ongoing basis.