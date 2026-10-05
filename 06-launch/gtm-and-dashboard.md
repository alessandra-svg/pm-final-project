# GTM Launch Plan, RouteLogic (B2B)

| Field | Value |
|---|---|
| Feature | One-Click Compliance Checklist |
| Goal | Engagement |
| Launch tier | M, Targeted |

## Goal & Audience
- **Goal:** Engagement, Not conversion, because there's no purchase or upgrade decision here — the 3 pilot accounts are already RouteLogic customers, and Coordinators are already active daily users. Not awareness, because Coordinators already know the Compliance Check exists; they interact with it every day. The goal is engagement: getting Coordinators to actually adopt the new pre-filled, one-click flow instead of falling back to old habits (manual re-typing, cross-checking via WhatsApp), so the behavior change described in the M3 hypothesis actually materializes.
- **Target audience:** Coordinators at the 3 pilot accounts who complete at least one Compliance Check per week — not Drivers, not Dispatchers, and not Coordinators at non-pilot accounts.

## Launch Tier
- **M, Targeted**, Reach is small by design — 3 pilot accounts, a subset of Coordinators, not a company-wide or market-wide rollout. Revenue impact is not the point of this phase; it's a validation pilot, not a monetized release. But the risk of silence is real, not negligible: Coordinators are creatures of habit around a 14.6-minute workflow they've built workarounds for (WhatsApp cross-checks). If the new flow ships with zero communication, the likely outcome isn't neutral — it's Coordinators not noticing the change, misinterpreting the new flags/colors, or reverting to old habits out of caution, which would suppress the very adoption the engagement goal depends on and contaminate the pilot's read on the hypothesis. That risk rules out S (minimal): some targeted enablement is required. But it doesn't warrant L or XL — there's no need for multi-channel campaigns or broad GTM assets for 3 accounts.

## Channels
1. **Owned: Owned — Direct communication to Coordinators at the 3 pilot accounts (channel TBD: email, SMS or team chat, whichever RouteLogic already uses to reach Coordinators outside the app) ahead of launch, so awareness doesn't depend on them opening the product first.**
2. **Owned: Short live walkthrough or recorded demo for Coordinators at the 3 pilot accounts — Owned. Given the habit-breaking nature of the change (new flags, colors, one-click confirm replacing manual retyping), a brief guided demo reduces the confusion risk flagged in Step 2's "risk of silence" more effectively than passive messaging alone.**
3. **Owned: In-app banner/tooltip — Owned. Coordinators already open Compliance Check daily; this reaches them at the exact moment of use, when the change is immediately visible and actionable (unlike the lapsed-user trap, this audience is actively in the product).**

## Enablement & Assets
CS/Account team needs: a one-page internal brief explaining what changed, why (14.6min → target ≤5min), and what to tell Coordinators if they ask why the workflow looks different.

Support needs: a short FAQ covering the new UI states (amber "stale" flag, red "expired document" flag, "Confirm all" disabled states) so they can answer tickets without escalating.

Assets to build: in-app banner copy; one-page internal brief; a short Coordinator-facing message for Channel 1 (content ready, format pending channel confirmation — email, SMS, or team chat); a 2–3 minute walkthrough recording (or live session agenda) for the pilot Coordinators.

## Ownership, Budget & Timeline
- **Ownership & budget:** CS/Account team brief and pilot account communication: Account lead for each of the 3 pilot accounts (names not specified in case study data — role-level ownership assigned pending real assignment)
Support FAQ: Support lead for pilot accounts (same caveat — role-level, not a named individual, due to case study data limits)
Walkthrough/demo: PM, since this is the person who best understands the FR-level detail (flags, states) that Coordinators will ask about.
In-app banner copy & timing: PM — owns content and trigger logic, coordinates with whoever holds eng/design resourcing for the pilot build.
- **Timeline:** Phase 1 (beta): Internal CS/Account brief and Support FAQ distributed before pilot start, so internal teams are aligned before any Coordinator sees the change.
Phase 2 (launch moment): In-app banner goes live at the same moment the variant is enabled for the test group (Day 1 of the 4-week pilot); walkthrough/demo delivered to pilot Coordinators in the same window.
Phase 3 (post-launch): No further enablement push planned — the pilot itself (4 weeks) is the observation window; enablement doesn't extend past it since the goal is behavioral adoption during the test, not sustained marketing.

## Success Metrics
- **Metrics:** Enablement reach: ≥80% of pilot Coordinators exposed before first post-launch check (provisional threshold)
Adoption rate: ≥50% using "Confirm all" on first exposure (provisional — if enablement reach is confirmed above 80%, adoption below 50% signals experience friction, not an enablement failure)
Support ticket volume: no fixed threshold set yet — flag any ticket volume above pre-launch baseline levels for the same period
- **Bad signal to watch for:** High enablement reach but low adoption = feature is understood but not trusted or not usable — Coordinators saw the banner/demo but still default to manual entry, meaning the friction isn't communication, it's the experience itself (or a fear that pre-filled data is wrong). Low enablement reach paired with low adoption = the opposite problem — Coordinators genuinely didn't know the change happened, meaning the enablement effort failed before the feature got a fair test. Distinguishing these two is why enablement reach and adoption need to be tracked as separate metrics, not folded into one.
- **Likely post-launch decision:** Iterate. A full pivot is unlikely — the underlying mechanism (pre-fill, confirm-all) is validated by existing system data (FR1 sources data already held by RouteLogic), so it's not a fundamentally wrong bet. A clean double-down is also unlikely this early — 3 accounts and 4 weeks is too small a signal to commit to broad rollout. The realistic trigger for iterate: adoption rate is positive but below expectations, or support tickets reveal a specific point of confusion (e.g., the amber "stale" flag isn't understood) — actionable, narrow problems that don't require rethinking the goal or audience, just refining the enablement assets or a specific UI element before the next account wave.
