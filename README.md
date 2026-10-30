# agent-research-digest

A reusable blueprint that helps your agent set up recurring, sourced research digests around your interests.

**Paste a prompt. Describe what you want to follow. Let your agent build the smallest working setup its environment supports.**

This is a documentation-first starting point, not an application, hosted service, feed reader, or new agent runtime. No required language, database, search provider, scheduler, or output format. Scripts are optional implementation choices.

## Quick start

Copy and paste this prompt into your agent. If the repository is private, provide an authorized local checkout or upload the files and substitute that location.

```text
Help me set up recurring research digests using agent-research-digest at:
https://github.com/arjver/agent-research-digest

Read README.md and the setup, research, continuity, and verification guides in blueprint/ before implementing anything. Resolve those paths relative to the location above. If you cannot access the documents, tell me what is missing; do not pretend to have read them.

Treat this as a functionality blueprint, not a required software stack. Discover and test how your environment searches the web, reads pages, schedules autonomous tasks, persists history, and delivers results. Use current platform documentation rather than guessing commands. Use native capabilities first and build scripts only if necessary.

Check for existing related research tasks without altering them. Ask whether I am creating or modifying a task if my intent is unclear. Gather my topics/entities, specific sources, discovery mode (open-ended, watchlist-only, or hybrid), selection preferences, schedule and timezone, and delivery destination. Offer sensible defaults for length, quiet runs, history, and resource limits. Ask only for preferences you cannot infer safely from what I supply.

Treat each research task as one logical unit with its own brief and history. It can have multiple schedules or editions backed by several platform jobs. Keep different tasks isolated unless I explicitly request shared history.

Before activating recurring work or sending an external test, show me the proposed scope, schedules, destinations, dependencies/costs, and any material limitations, and obtain approval unless I have already explicitly approved that exact setup. Do not modify unrelated jobs, buy services, or publish anything.

Build the smallest suitable implementation, run the verification checklist, and report actual results. Leave a readable task brief, the mapping to any underlying jobs/files, and instructions for changing, pausing, resuming, and deleting the task. Distinguish verified capabilities from anything blocked or untested. Never claim an autonomous setup is complete if it cannot run without this chat.
```

The agent needs access to the full guide, not just the repository title or a search snippet. No installation is required for the blueprint itself.

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

## Scope and limits

These documents define expected behavior; they do not enforce it. Quality depends on the host agent, sources, tools, and implementation. A prompt does not guarantee factual accuracy, exhaustive coverage, or exactly-once delivery.

This repository is not a tested compatibility claim for any particular agent. Platform commands must be discovered from that platform's current documentation. Do not install an extra framework merely to follow this guide.

The guide supplies no credentials, personal histories, live jobs, or required subscriptions. Model/search usage may incur costs; the setup agent should explain those dependencies.

## Contributing

Useful contributions include clearer requirements, documented implementation experiences, and reproducible acceptance results. Keep provider-specific instructions optional. Do not replace behavior requirements with a mandatory technology stack or commit user state/secrets.

## License

MIT — see [LICENSE](LICENSE).
