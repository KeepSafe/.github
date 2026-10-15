<!-- Title: TEAM-123 Verb + specific behavior or outcome + relevant condition.
Example: IOS-123 Preserve upload progress when the app restarts.
Replace prompts with facts. Keep the human sections concise and readable on their
own. Scale detail to the change; remove inapplicable optional prompts. Preserve
essential reasoning and results in the body because it becomes the commit message.
-->

## Problem and outcome

<!-- Explain the core problem or need as one engineer would explain it to another
at a whiteboard. Describe the relevant before/after behavior and why it matters.
When useful, show the essence with a few lines of code, a usage example, a diagram,
or an event sequence. Label illustrative code as simplified; preserve the actual
failure mechanism. For features, show what becomes possible. -->

## Approach

<!-- Explain the central idea of the change. Preserve a meaningful constraint or
tradeoff that a future reader needs to understand why the code is this way.
Include compatibility, persistent-state changes, or cross-repository sequencing
when relevant. Omit this section if the explanation above already covers it. -->

## Evidence

<!-- Summarize the strongest observed evidence for the intended outcome in a few
sentences. State what happened, rather than just "tests pass." Include a concise
before/after result, screenshot, or demo when useful. Illustrations above explain
the mechanism; actual verification here supports the implementation's behavior.
Keep essential results in the body; links supplement them. -->

## Agent reference

### Goal and acceptance criteria

<!-- State the intended outcome and observable criteria precisely enough for
another agent to assess the implementation. Reuse the human explanation by
reference where sufficient. Include deliberate scope boundaries when relevant. -->

### Verification record

<!-- Repeat this entry for materially different claims, grouping related checks.
Record completed verification, not planned checks. Include important failure,
recovery, and regression behavior where relevant. -->

- Claim: [Acceptance criterion or behavior established.]
  - Verification: [Exact command/test reference or repeatable manual procedure.]
  - Result: [Specific observed result, including failures or partial results.]
  - Scope: [Revision verified; relevant environment, inputs, flags, and any mocks
    or substitutions. Identify lifecycle boundaries actually exercised.]
  - Evidence: [Durable test/file reference or artifact link, if useful.]

### Gaps and residual risks

<!-- Identify relevant behavior not exercised, assumptions, and remaining risks.
Distinguish component proof from end-to-end proof. State if checks predate relevant
final changes. Use "None identified" only when justified by the recorded scope. -->

## Production verification

<!-- Linear owns release tracking. Link the issue once if it is not already
linked in this description. Keep release dates, rollout status, ownership, and
later monitoring results in Linear. This section preserves change-specific
instructions for whoever observes the release, including agents.
For changes with no production behavior, replace the prompts with a short reason.
-->

- Expected outcome: [Observable behavior that should improve or appear.]
- Where to check: [Dashboard/saved query or repeatable read-only procedure;
  include relevant filters and a baseline, comparison cohort, or invariant.]
- Meaningful exposure: [How to establish the change is active, when to check,
  and what usage/adoption or elapsed time makes the result meaningful.]
- Investigate if: [Specific unexpected behavior or regression threshold.]
- Recovery: [Available containment or reversal and its limitations; include
  compatibility, irreversible state changes, or a corrective release if relevant.]

<!-- Clients: filter by released version/build, adoption, and relevant OS/device
groups; account for delayed updates and staged rollouts. Backend: identify the
deployed revision/environment, relevant traffic, and flag exposure. For changes
spanning both, describe prerequisites and observation/recovery for each side.
Insufficient exposure or missing telemetry means inconclusive, not successful.
Recovery instructions do not themselves authorize an agent to intervene. -->
