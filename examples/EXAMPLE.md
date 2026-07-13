# Example session (illustrative)

A condensed, illustrative transcript — a payments app where agents shipped a retry queue and a new pricing constant that week. Real sessions are longer.

---

**Agent:** Scoped to the last 5 merged PRs. Heaviest changes: the webhook retry queue (PR 41), the `PRICE_CAP = 4900` constant (PR 43), idempotency keys on charge creation (PR 44). Eight questions, one at a time.

**Q1.** The retry queue uses exponential backoff with a 6-attempt cap. Why 6 — and what happens to a webhook that fails all 6?

**You:** It retries for about an hour total? After that I think it's dropped.

**Agent:** Partial. Follow-up: dropped silently, or is there a dead-letter path?

**You:** ...I don't know.

**Agent:** Noted. **Q2.** Where does `PRICE_CAP = 4900` come from?

**You:** That's £49, our top plan price in pence — a charge above it must be a bug.

**Agent:** Correct, including the unit trap. **Q3.** Charge creation now sends an idempotency key. Walk me through what happens when the same request arrives twice within a second...

*(five more questions)*

---

**Grade: 5/8**

| # | Verdict | Note |
|---|---|---|
| 1 | Missed | Failed webhooks land in `dead_letters`; nothing replays them yet — that's the risk you didn't know you had |
| 2 | Correct | |
| 3 | Correct | |
| 4 | Partial | You knew *what* the flag does, not *why* the alternative was rejected in PR 41's review |
| … | | |

**Re-explanation of misses:** `queue/retry.ts:88` — after attempt 6 the event lands in `dead_letters` with no consumer. If your payments provider has an outage longer than ~70 minutes, you lose webhooks permanently unless someone replays the table by hand...

**Retake:** below 6/8 — re-quiz on the retry pipeline and PR 41's design decisions next session. Say "retake" when ready.
