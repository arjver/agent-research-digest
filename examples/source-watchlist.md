# Example: specific-source watchlist

Illustrative user brief—not a preconfigured integration:

> Every Friday at 16:00 Europe/London, check these three project blogs and this standards working-group page: [user supplies URLs]. Tell me about substantive new posts, releases, or changes to the draft standard. Only use these sources; do not search for broader industry news. A short explanation and link per development is enough. Deliver to my chosen email address. No empty digests.

The agent requests the actual URLs and exact destination, validates source access, and identifies whether each source is a feed, a listing page, or a document updated in place. It must not invent URLs to complete this example.

This task has its own weekly schedule and history. It can coexist with the open-ended task without sharing history. A standards page changing at the same URL requires meaningful content-change detection, not just URL deduplication.

If a source is blocked, the agent records the gap; it does not silently broaden the source list. Funding or leadership changes are included only if the user's brief makes them relevant—not because all watchlists should cover them.
