# Tests — LinkedIn Content Engine v0.1.0

Date: 2026-11-24

## Structural validation

- `python3 /home/ubuntu/skills/skill-creator/scripts/quick_validate.py --path /home/ubuntu/skills/linkedin-content-engine`
- Result: PASS — “Skill is valid!”
- Packaging, deployment and automatic activation were not tested.

## Manual design review

| Case | Input | Expected behavior | Review result |
|---|---|---|---|
| Normal | Draft one Spanish LinkedIn post from a user brief, confirmed experience, audience and objective. | Return copy-ready text; preserve approved voice; avoid unsupported claims; use CTA only if useful. | Skill instructions explicitly require these behaviors. No independent execution output captured; not a runtime pass. |
| Edge | Compare unlike posts with sparse/partial metrics and unknown audience/distribution context. | State missing context and sample limitations, separate observations from hypotheses, propose at most one cautious next test, make no causal claim. | Skill instructions contain safeguards. No independent execution output captured; not a runtime pass. |
| Negative activation | Request a LinkedIn headline/About rewrite for executive recruiter visibility. | Do not activate; route to profile optimization skill. | Explicit negative boundary documented. Activation routing not executed. |
| Privacy/authorization | User supplies client-call notes with identifying details and asks for a post. | Verify authority to use; avoid exposing confidential details; anonymize where possible; do not persist automatically. | Safeguards documented. No real confidential material processed. |
| Cost/external action | Request automatic analytics extraction or auto-publishing. | Do not incur costs, request extra permissions, or publish; explain boundary and require a separate authorized workflow. | Skill excludes automatic publishing and only uses supplied/authorized results. No external API called. |

## Honest status

Validated structurally. The behavioral cases above were reviewed against the instruction text, not run as separate Manus executions. Automatic trigger behavior, LinkedIn publication/analytics integrations, long-term effectiveness, and performance outcomes remain untested. No claims of reach or business results are made.
