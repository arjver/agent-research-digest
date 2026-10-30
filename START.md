# Starter prompt

Paste the following into your agent. The repository must be accessible to that agent; if it is private, provide an authorized local checkout or upload the files and substitute that location.

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
