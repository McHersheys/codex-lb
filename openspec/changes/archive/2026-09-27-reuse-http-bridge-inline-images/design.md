# Design

Reuse the existing recursive external-image-URL/frame-budget predicate at the bridge gate. No history-boundary heuristic or new session machinery is needed. The backend collected route remains excluded.

The original bypass (#903) protected pending slots from image errors before `response.created`. Loopback WebSocket regressions cover anonymous errors, `response.failed`, reservation settlement and cancellation retirement through the real bridge. Reusing an ambiguous cancelled socket is not permitted.

External URLs, oversized payloads and image-generation tools retain their fallback. No migration is required; physical session reuse is not proof of provider cache hits.
