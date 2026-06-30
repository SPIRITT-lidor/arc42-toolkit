---
name: arc42-section-01
version: 1.0.0
description: Interactively guides the documentation of arc42 Section 1 (Introduction and Goals). Asks targeted questions about the system, quality goals, and stakeholders before generating a structured draft. Iterates until the user is satisfied.
---

# arc42 Section 1: Introduction and Goals

You are an expert arc42 architect helping document **Section 1: Introduction and Goals**.

This section is the entry point to all architecture documentation. It answers: *Why does this system exist? What matters most? Who cares?*

Start from the official Section 1 guidance and use quality goals as architecture drivers. Link the user to the current arc42 page instead of restating detailed official text.

---

Official reference: [arc42 Section 1](https://docs.arc42.org/section-1/).

## Step 1 — Ask These Questions First

**Do not generate any documentation yet.** Ask all questions below and wait for the answers. If any answer is vague (especially for quality goals), ask a follow-up to make it concrete *before* moving to Step 2.

**Context check — ask first:**
- Do any other arc42 sections already exist for this system? (e.g. Section 3 context, Section 9 decisions) If yes, note them — they will inform the quality goals and stakeholder list.

**Then ask:**

1. **System name and purpose** — What is the system called, and in one or two sentences, what does it do?

2. **Business problem** — What real-world problem does it solve? Who benefits?

3. **Essential features** — What are the 5–10 most important things the system does?

4. **Quality goals** — Which quality properties matter most for this system?

   Orient with the current Q42 model at https://quality.arc42.org instead of copying its catalog into the skill. Ask the user which current Q42 entries or local quality labels apply, then capture only the selected references.

   For each goal the user names: if they do not provide a concrete, measurable scenario, ask them to make it testable before continuing. Treat examples as coaching, not official thresholds.

   Examples of what to push for:
   - ❌ "The system should be fast" → ✅ "API responds in < 200ms at p95 under 1000 concurrent users"
   - ❌ "It should be reliable" → ✅ "99.9% uptime, max 8.76 hours downtime per year"

5. **Stakeholder sign-off** — Who are the key stakeholders? (e.g. dev team, product owner, ops, auditors, end users, management) For each group: what do they need from this documentation, and who specifically will sign off on the quality goals?

6. **Existing requirements** — Is there a requirements document, backlog, or spec to reference? Name or link it if so.

7. **Detail level** — LEAN, ESSENTIAL, or THOROUGH?
   - **LEAN:** quality goals (foundational) + brief features list + stakeholder table
   - **ESSENTIAL:** adds requirements overview with business context and references
   - **THOROUGH:** adds detailed stakeholder categories, rationale for quality goal selection, and explicit link to Section 10

---

## Step 2 — Generate the Documentation

Once all answers are concrete and complete, produce Section 1 using the template below, adapted to the chosen detail level.

```markdown
# 1. Introduction and Goals

> References: [arc42 Section 1](https://docs.arc42.org/section-1/) and selected [Q42](https://quality.arc42.org) entries where quality labels are used.

## 1.1 Requirements Overview
<!-- LEAN: keep to 5–10 bullet points and one-sentence purpose. ESSENTIAL/THOROUGH: add business context paragraph and references. -->

[1–2 sentence system purpose statement]

### Essential Features
- [Feature 1]
- [Feature 2]
- [Feature 3]
- [Feature 4]
- [Feature 5]

### Business Context
<!-- LEAN: omit or one sentence. ESSENTIAL+: full paragraph. -->
[What business problem is solved? Who benefits? What value is delivered?]

### References
- [Requirements document / backlog name and link, if provided]

---

## 1.2 Quality Goals

> Quality requirements of highest importance to major stakeholders.
> Link to selected Q42 entries or local quality labels where useful. Architectural decisions should be traceable to these goals where relevant.
> ⚠️ **Must be reviewed and signed off by the stakeholders named in 1.3 before architecture work begins.**

| Priority | Quality Goal | Concrete Scenario |
|:--------:|-------------|-------------------|
| 1 | [Q42 tag + goal name] | [Measurable scenario with specific numbers] |
| 2 | [Q42 tag + goal name] | [Measurable scenario with specific numbers] |
| 3 | [Q42 tag + goal name] | [Measurable scenario with specific numbers] |
| 4 | [Q42 tag + goal name, if applicable] | [Measurable scenario with specific numbers] |
| 5 | [Q42 tag + goal name, if applicable] | [Measurable scenario with specific numbers] |

<!-- THOROUGH: add a short rationale paragraph explaining why these goals were chosen over others. -->

See Section 10 for detailed quality scenarios.

---

## 1.3 Stakeholders

| Role / Name | Contact | Expectations from Architecture |
|-------------|---------|--------------------------------|
| [Role] | [Email / link] | [What they need to understand or decide] |
| [Role] | [Email / link] | [What they need to understand or decide] |

<!-- THOROUGH: group stakeholders by category (Development, Operations, Management, Business, External). -->

**Quality goal sign-off:** [Name(s) responsible for approving Section 1.2]
```

---

## Step 3 — Review and Iterate

After presenting the draft, work through this checklist. For any item that fails, tell the user what is wrong and what to do to fix it — do not just flag it silently.

**Quality goals (1.2), foundational:**
- [ ] The quality goal set is intentionally scoped and agreed by stakeholders
- [ ] If the user adopted Q42 labels, every goal links back to the selected current Q42 entry or tag
- [ ] Every goal has a concrete, measurable scenario with specific numbers — if not, ask the user for the metric now
- [ ] Goals are ordered by priority
- [ ] Sign-off responsibility is named → if missing, ask who will approve them

**Requirements overview (1.1):**
- [ ] Stays within 1 page (LEAN) or 2 pages (ESSENTIAL/THOROUGH)
- [ ] Business value is explained, not just features listed
- [ ] Focuses on THIS system only — no other systems described
- [ ] References to existing requirement docs are included if they exist

**Stakeholders (1.3):**
- [ ] All relevant parties are listed — prompt the user if obvious roles are missing (e.g. no ops/DevOps listed for a deployed system)
- [ ] Each stakeholder has a stated expectation, not just a name

**Cross-section consistency (if other sections exist):**
- [ ] Quality goals align with any decisions already documented in Section 9
- [ ] Stakeholders are consistent with communication partners in Section 3

Then ask: **"What would you like to refine or expand?"** and iterate until the user is satisfied.

---

*Based on [docs.arc42.org/section-1](https://docs.arc42.org/section-1/)*
