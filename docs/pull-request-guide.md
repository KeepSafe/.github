# Shared pull request template

Use [PULL_REQUEST_TEMPLATE.md](../PULL_REQUEST_TEMPLATE.md) for client applications,
mobile applications, backend services, and shared tooling. One common structure
keeps intent and evidence consistent; production verification includes prompts
for the relevant release model.

## Adoption

This public `.github` repository is the canonical source for KeepSafe's
organization-wide default. GitHub uses it for repositories that do not define
their own pull request template; a repository-level template takes precedence.
KeepSafe repositories should not copy or maintain local pull request templates:
remove existing local templates so GitHub displays this default. The shared
`submit-github-pr` skill fetches this organization template directly for every
KeepSafe PR, even while a repository-local template remains.

## Title

Prefix every title with the actual Linear issue ID, then use an imperative
sentence describing the specific behavior or outcome:

```text
TEAM-123 Verb + specific behavior or outcome + relevant condition
```

Examples (illustrative IDs):

- `IOS-123 Preserve upload progress when the app restarts`
- `BE-123 Prevent duplicate charges when checkout is retried`
- `WEB-123 Let workspace owners export their audit history`

Prefer an observable outcome over a filename or implementation task. For an
internal refactor, name the concrete structural change and preserve its purpose
in the description. Use the repository's established issue separator if needed.

## Writing the description

The title and description become the commit message. Write them for an engineer
or agent investigating changed code later, as well as today's reviewer.

The human sections explain the problem, central idea, and strongest evidence.
Use a minimal illustration when it makes the core mechanism easier to understand.
For example, a simplified sequence can expose a race:

```text
Refresh A starts -> Refresh B starts -> B completes -> A completes
                                      fresh data     overwrites with stale data
```

Follow it with the intended behavior: "Only the latest refresh may update the
displayed data." The illustration explains the bug; the evidence section must
describe what was actually observed when verifying the fix.

The agent reference maps acceptance claims to repeatable verification, results,
and limitations. Keep it proportional: a documentation change may need only a
short record of content and link inspection. Record failed or unexecuted checks
honestly. Do not turn a planned check into a completed result or imply that
component tests prove an unexecuted user journey. Refresh affected evidence
after relevant changes to the final revision.

Keep essential findings in the description. Local absolute paths, expiring logs,
and CI links alone do not make a durable commit artifact. Use repository-relative
test/file references and durable links as supporting evidence. Remove drafting
prompts and temporary coordination notes before merging.

## Production verification and Linear

Linear remains the source for release membership, dates, rollout progress,
ownership, and follow-up observations. The PR preserves what to check and why.
An agent can start from a release in Linear, follow its issues to the PRs, and
use these instructions to assess the exposed changes.

For clients, account for version adoption, old and new clients coexisting,
OS/device differences, local data, and recovery through a flag, paused rollout,
or corrective release. For backend changes, account for deployment revision,
traffic, flags, migrations, active client compatibility, and rollback constraints.
Include only the dimensions relevant to the change. For coupled releases,
record prerequisites and deployment order in the approach.

Define enough exposure and a comparison to interpret the result. Low adoption,
low traffic, or unavailable telemetry makes a result inconclusive. Describe an
observability gap explicitly; do not invent a metric or require new telemetry
for every change. Changes with no production behavior should say why production
verification is inapplicable. Monitoring observations go back into Linear;
intervention requires the authority of the applicable operating workflow.
