# Setup guide

## 1. Establish scope and protect existing work

Read all four blueprint guides. Treat user instructions as authoritative over example defaults. Inspect available task registrations or a user-approved task directory; do not scan unrelated private data. Determine create vs update before changing existing state. Give every logical task a stable identity distinct from its editable display name.

An existing task is not replaced just because a new one has similar topics. Repeated setup should discover and reuse the intended task rather than create duplicate schedules. Record the mapping of logical task → editions → platform job identifiers and owned artifacts. Do not guess identifiers.

## 2. Discover capabilities using harmless probes

Record the tested path, evidence, limitations, and fallback for each capability:

- **Search:** run a benign topic query, inspect actual results and source dates. Do not assume an instant-answer endpoint is a search engine. For watchlist-only mode, broad search may be unnecessary.
- **Page reading:** read a representative user source beyond its title/snippet; distinguish article body from navigation, login walls, and empty responses. Verify supplied feeds return actual feed content, not an HTML fallback page. Check dates and usable article links.
- **Scheduling:** consult current host documentation. Determine whether tasks run autonomously, require a continuously running host, inherit tools/credentials, support timezone/DST, and have execution limits. An interactive reminder is not necessarily an autonomous research run.
- **Persistence:** test an isolated temporary write/read if available and establish that scheduled sessions can reach the same durable location. Conversation memory alone is insufficient unless its cross-run behavior is documented and tested.
- **Delivery:** establish supported destinations, identities and size/format constraints. Use previews first; send a labeled external test only with authorization. Record delivery evidence.

Do not install dependencies or configure accounts just to test an unneeded capability. Ask before adding paid services, privileged software, or new external access. Never ask users to paste secrets into public documents; use the host's secure credential facilities.

If an essential capability is missing, explain the blocked requirement and propose a manual mode or approved alternative. Label partial setups accurately. Never fabricate tool results or claim a platform supports a feature because a different platform does.

## 3. Gather a compact research brief

Ask only unresolved questions, grouping independent questions together:

- Task name, purpose, topics/entities, and audience.
- Discovery mode: **open-ended**, **watchlist-only**, or **hybrid**.
- Specific source URLs and whether each is required or preferred. Sources may be feeds, listing pages, or pages whose content changes in place.
- Inclusion/exclusion criteria: significance, types of developments, and useful follow-ups.
- Schedule(s), timezone, delivery destination(s), and any edition-specific differences.
- Desired detail/language, optional layout, quiet-on-no-change preference, budget/runtime constraints.

Offer defaults: concise sourced summaries; silent successful runs when nothing qualifies; include material follow-ups; isolated per-task history. Do not impose AI-specific topics or large-release-only selection criteria.

Prefer an IANA timezone such as America/Los_Angeles when local clock times should survive daylight-saving changes. Clarify fixed UTC vs local-clock intent. Specify daily/weekday/weekly behavior and interpret ambiguous times explicitly.

Distinguish execution time from arrival deadline: if the user wants a digest delivered by a time, allow time to research and explain that delivery cannot be guaranteed to the second.

For a new task, agree on the initial lookback rather than reporting an entire website backlog. Subsequent runs should cover the interval since the last successful coverage checkpoint, with suitable overlap. If outages create a long backlog, use a bounded catch-up policy and disclose gaps rather than silently dropping them.

## 4. Design and approve the smallest implementation

Summarize the brief, capability paths, proposed schedules, external destinations, costs/dependencies, and limitations. Obtain approval for activation/external test delivery unless the user already approved those exact side effects. Do not confuse request-to-plan with authorization-to-activate.

Prefer native search, page tools, scheduler, storage, and delivery. Scripts are optional, useful for mechanical collection or state management—not a mandatory runtime. No particular filename, storage format, provider, or directory is required.

Use the [task brief](../templates/task-brief.md) if helpful. Save an equivalent readable record even if the platform uses a different schema.

Scheduled runs must receive the full brief or a durable reference to it, research/continuity instructions, relevant history, credentials through approved facilities, and delivery settings. Assume a fresh session without the current conversation. Grant only needed capabilities and preserve private file permissions.

Avoid duplicate delivery paths: choose native scheduler delivery or an explicit sending mechanism and record which owns sending. Do not send a report manually and then let the scheduler send the same final response again.

## 5. Build, verify, then hand off

Create only the authorized task's resources. Where supported, keep schedules disabled until verification is complete. Use [verification.md](verification.md), including a fresh-session test and repeat-run scenario. Read back exact external task registrations after creation or update. Recheck that unrelated tasks were unchanged.

Report the task's name, schedules/timezone, mode, destination, artifact locations and job mapping, verified checks, and remaining limitations. Clearly state whether automation is active, paused, or blocked.

## 6. Lifecycle operations

- **Change scope/preferences:** update the durable brief and affected runs; preserve identity/history. Reset history only with explicit approval.
- **Change an edition:** update only that edition's schedule/instructions; preserve shared task history.
- **Pause/resume a task:** operate on every mapped schedule. Pausing a job does not necessarily stop an already-running session; inspect and explain that separately.
- **Delete:** confirm scope, remove only owned jobs, and agree whether to retain history. Do not delete shared resources another task still needs.
- **Move between agents:** export the brief and approved history, rediscover capabilities, rebuild scheduling, and verify again. Coordinate deactivation of the old scheduler so both do not send duplicates.
- **Share history:** opt-in across logical tasks; define what 'already reported' means for different recipients/editions. Within one task, shared history is the default.
