# agent-research-digest

A reusable blueprint that helps your agent set up recurring, sourced research digests around your interests.

**Paste a prompt. Describe what you want to follow. Let your agent build the smallest working setup its environment supports.**

This is a documentation-first starting point, not an application, hosted service, feed reader, or new agent runtime. No required language, database, search provider, scheduler, or output format. Scripts are optional implementation choices.

## Start

1. Download this repository or make its files available to your agent.
2. Copy the prompt in [START.md](START.md). It references this repository; substitute your local checkout directory if your agent cannot access the URL.
3. Your agent checks its capabilities, asks for your research preferences, and implements and tests the workflow.

The agent needs access to the guide's contents, not just a repository title or search snippet. A URL works only if that agent can read the repository files. Upload the files or provide a local checkout otherwise.

## Choose what to follow

- **Open-ended:** discover developments throughout a topic or field.
- **Watchlist-only:** monitor specific sites, blogs, feeds, or pages without expanding discovery beyond them.
- **Hybrid:** check named sources and search more broadly.

Topics need not involve AI: scientific research, developer tools, local policy, industries, organizations, or specialist publications all fit.

## One task, multiple runs

A research task owns its scope, preferences, history, and delivery settings. It can have multiple schedules or editions. A morning and evening briefing is **one task**, even if the platform needs two scheduled jobs. A separate weekly watchlist is another task.

Multiple tasks are independent by default. Shared history across related tasks is opt-in. Pausing a task pauses all its underlying schedules; changing one edition affects only that edition.

## What the blueprint asks the agent to do

1. Discover and test search, page access, scheduling, persistence, and delivery.
2. Agree on scope, schedule/timezone, sources, significance criteria, and destination.
3. Use native features first; add scripts only when they solve a real capability gap.
4. Keep each run self-contained and retain history without mistaking discovered items for delivered stories.
5. Verify a sample run, repeat-story handling, scheduling, and delivery before declaring success.

A platform without durable scheduling cannot promise autonomous delivery. The agent must explain the limitation and offer an explicitly manual workflow or an approved external scheduler.

## Contents

- [Setup guide](blueprint/setup.md): discovery, preferences, implementation, lifecycle.
- [Research behavior](blueprint/research.md): source handling, selection, evidence, output.
- [Continuity](blueprint/continuity.md): history, follow-ups, delivery failures, overlapping runs.
- [Verification](blueprint/verification.md): acceptance checks and scenario tests.
- [Task brief](templates/task-brief.md): optional portable handoff template.
- [Open-ended example](examples/broad-topic.md), [watchlist example](examples/source-watchlist.md), [hybrid example](examples/hybrid.md).

See [local draft verification](REVIEW.md) for checks performed and what has not been tested.

## Scope and limits

These documents define expected behavior; they do not enforce it. Quality depends on the host agent, sources, tools, and implementation. A prompt does not guarantee factual accuracy, exhaustive coverage, or exactly-once delivery.

This repository is not a tested compatibility claim for any particular agent. Platform commands must be discovered from that platform's current documentation. Do not install an extra framework merely to follow this guide.

The guide supplies no credentials, personal histories, live jobs, or required subscriptions. Model/search usage may incur costs; the setup agent should explain those dependencies.

## Contributing

Useful contributions include clearer requirements, documented implementation experiences, and reproducible acceptance results. Keep provider-specific instructions optional. Do not replace behavior requirements with a mandatory technology stack or commit user state/secrets.

## License

MIT — see [LICENSE](LICENSE).
