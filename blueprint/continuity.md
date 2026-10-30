# Continuity and delivery semantics

These are behavioral requirements, not a database schema. JSON files, a native task store, or a database can all work.

## Keep different states distinct

Track enough to distinguish:

1. **Discovered:** a candidate was seen; it may be unread, deferred, stale, or irrelevant.
2. **Evaluated:** it was assessed, with its disposition and relevant event identity.
3. **Prepared:** a digest containing it is saved and pending delivery.
4. **Delivered:** the destination acknowledged delivery, with evidence available from the platform.

Never mark all discovered candidates as reported merely because an article-fetch limit was reached. Persist deferred candidates or retain a discovery cursor that makes them eligible next time. 'Seen URL' caches optimize fetching; they do not prove the user received a story.

Keep prepared output durable before sending so a delivery failure can retry without rewriting the research. Promote stories to delivered after confirmation. If the scheduler sends after the agent exits, use a documented completion record/callback or reconcile delivery history on the next run. If the platform cannot provide confirmation, record **delivery unknown**, not delivered, and explain the limitation.

## Story memory

Store a compact identity/summary of reported facts, source links, reporting/event times as known, and enough detail to recognize material follow-ups. A source URL alone is not a story identity. Track relevant content versions for pages that change in place.

History retention should suit cadence and subject: enough to catch syndication and follow-ups, bounded to avoid unmanageable context. A possible starting point is 14 days for frequent briefings and 30 days for weekly ones, not a required constant. Preserve unresolved pending delivery and deferred work beyond ordinary pruning.

## Coverage and catch-up

Track coverage checkpoints per collection scope or edition when their lookbacks or selection rules differ. Shared story history does not imply one global cursor: a daily edition must not advance past material a weekly synthesis still needs.

Track successful coverage independently from delivery status. A successful research run with no new stories can advance coverage; a failed run cannot. Partial failures should retain per-source gaps or an equivalent retry record. A prepared-but-undelivered digest may have completed research but still requires delivery reconciliation.

When recording a failed check, preserve the last successful checkpoint for that scope alongside the failure or gap. Failure metadata must not erase or replace the checkpoint needed for catch-up; advance it only when successful coverage justifies doing so.

Use overlap around coverage boundaries to handle indexing delays and publication timezones. On recovery, catch up from the appropriate checkpoint subject to the agreed limit. Explain omitted backlog or incomplete coverage. Do not treat a capped catch-up as exhaustive.

## Concurrency and retries

Serialize overlapping editions of the same task or use equivalent transactional/locking behavior. Writes should be atomic or use native transactions so a crash does not corrupt shared history. Preserve recoverable state and backups appropriate to the implementation.

If history is corrupt or unavailable, surface the issue; do not silently erase it and claim deduplication still works. Recover a backup or pause/reduce operation with an explicit limitation.

Use stable run/digest identities when possible. Track delivery per destination and, for split reports, per part. Retry missing/failed parts rather than resending confirmed parts. If a timeout leaves acceptance uncertain, reconcile first; if impossible, make the retry-vs-duplicate tradeoff explicit. Do not promise exactly-once delivery without platform support.

## Multiple tasks and editions

Every task has an isolated scope, state namespace, and owned-resource mapping by default. Editions within one task share story history while retaining their own schedule/lookback/selection overrides. A weekly synthesis may intentionally revisit previously covered events if the brief calls for it.

Cross-task shared history is opt-in. Define whether a report to one recipient should suppress another recipient's digest; do not make that assumption automatically. Reconfiguration must not conflate similarly named tasks or orphan live schedules.

## Privacy

History and briefs can reveal user interests. Keep them local/private unless the user chooses otherwise. Exclude state, credentials, private delivery identifiers, and raw user transcripts from public repositories. Treat explicit secret deletion and ordinary history cleanup as different operations.
