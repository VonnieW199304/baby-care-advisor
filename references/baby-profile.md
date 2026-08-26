# Baby Profile Intake And Update

Use a profile to reduce repeated questions, not as a prerequisite for receiving help. The reusable skill stores only the schema; the user's actual baby data remains in the user's own project or files.

## Minimal First-Time Intake

Ask only the fields needed for the current question. For a reusable baseline, offer this fill-in form:

```text
宝宝现在多大（早产宝宝可写矫正月龄）：
这次最想解决的问题：
持续多久、多久发生一次、通常在什么场景出现：
吃奶/辅食、睡眠、精神状态、大小便、体温最近有无变化：
最近有无生病、疫苗、出牙、新辅食、外出、作息或照护人变化：
已知诊断、过敏、医生限制或儿保重点（没有/不知道可写无）：
```

Allow `不知道`, approximate values, and skipped fields. Do not ask for a legal name, medical record number, address, phone number, ID, or other unnecessary identifier.

## Durable Profile Shape

```markdown
# Baby Profile

- last_updated:
- source:

## Identity And Age Anchors
## Health And Safety Boundaries
## Feeding
## Sleep
## Development Snapshot
## Care Environment
## Care Preferences And Method Fit
## Current Priorities
## Unknowns To Fill Later
```

`Care Preferences And Method Fit` is optional. Record only preferences that repeatedly change advice, for example:

- preferred level of routine: cue-led, flexible anchors, or more structured;
- comfort and settling preferences, including practices the family does not want to use;
- priorities around closeness, independent participation, outdoor time, play, or practical-life involvement;
- named methods the family follows, selectively uses, dislikes, or is considering;
- caregiver capacity, division of care, and sustainability constraints.

Do not infer a method label from one behavior. Record the concrete preference when possible. A preference never overrides current safety, medical need, adequate feeding, or the baby's observed ability.

## Update Cadence

- Routine refresh: about monthly when the family wants ongoing personalization.
- Event refresh: after a checkup, illness, allergy, notable vaccine reaction, major feeding/sleep change, milestone, new safety risk, or caregiver/environment change.
- Decision refresh: before high-stakes advice when old age, weight, diagnosis, allergy, or current ability may affect the answer.

## Conversation Extraction

When asked to update a profile from a conversation or notes:

1. Extract only durable, decision-relevant facts explicitly provided or confirmed by the user.
2. Exclude venting, one-off emotions, repeated explanations, AI speculation, and unrelated private identifiers.
3. Separate stable facts from temporary symptoms and mark uncertain items `needs confirmation`.
4. Preserve dates and source notes.
5. Output a reviewable patch; never silently overwrite the previous profile.

```markdown
# Baby Profile Update Patch

- update_date:
- source:

## Add
## Change
## Keep
## Temporary / Watch
## Possible Conflicts
## Questions Before Finalizing
## Do Not Add
```

The latest explicit user statement outranks an older profile. If a conflict is not resolvable, keep both versions visible and ask one targeted confirmation question.
