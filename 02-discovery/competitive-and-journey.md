# Persona & Future-State Journey, Module 2

- **Scenario:** RouteLogic Velocity (B2B)

## Persona
- **Role:** A multi-year driver who has used the app long enough to feel every added feature as friction rather than value
- **Goal:** complete the same handful of core actions (start route, mark delivered) as fast and reliably as physically possible, dozens of times per shift
- **Friction:** standing at a doorstep in the rain with a package in one hand, forced through three taps across three screens just to mark a delivery complete, while the "Start Route" button he uses 30 times a day sits buried under features he's never touched, to the point he's started texting his dispatcher instead of using the app at all

## Current workaround (the status quo to beat)
- **External tools:** - Texting the dispatcher directly (outside the app's own workflow)
- A paper manifest kept as physical backup
- **The process:** The process is:
1. Texts the dispatcher directly instead of using the in-app "mark delivered" flow, bypassing the 3-tap/3-screen process entirely
2. Keeps a paper manifest as backup for tracking route progress
3. Manually re-locates buried core functions each shift, since "Start Route" has no fixed, accessible position and keeps shifting under new feature additions
- **Core frustration:** "Standing at a doorstep in the rain with a package in one hand, forced through three taps across three screens just to mark a delivery complete", while the button he uses 30 times a day sits buried under features he's never touched.
- **The evidence:** UXR-01: "To mark a stop delivered I tap through three screens. In the rain, at a doorstep, with a package in one hand. I've started just texting my dispatcher instead."
UXR-12: five of seven drivers in the focus group keep a paper manifest "just in case the app dies"
UXR-11: "Every update adds a button. Nothing gets removed. The 'start route' I use 30 times a day is now buried under features I've never touched."
BUG-2055: "Mark delivered" requires 3 taps across 3 screens; no single-tap completion, top frontline complaint, drives off-platform workarounds

## Future-state journey map
1. Simple home screen

Action -> Benefit: Finds what he needs in one glance

User Action: Sees "Start Route" and "Mark Delivered" front and center, nothing else competing for attention

Internal State: Relief, no more hunting through menus he's never touched

Pain Point Addressed: Core actions buried 2–3 levels deep (BUG-2079)
2. One-tap completion

Action -> Benefit: Taps once at the doorstep to mark delivery complete -> Frees his hands, saves seconds per stop

User Action: Completes the delivery in a single motion, package still in hand, no screen-switching

Internal State: Physical relief, the task matches the real conditions he works in

Pain Point Addressed: Three taps across three screens (BUG-2055)
3. Instant sync confirmation

Action -> Benefit: Sees on-screen confirmation the update reached dispatch -> Removes doubt it "actually worked"

User Action: Glances at a status indicator instead of wondering if he needs to follow up

Internal State: Confidence, no need to double-check or over-explain later

Pain Point Addressed: Dispatcher dashboard lag showing stale "in progress" status (BUG-2072)
4. Trust rebuilt

Action -> Benefit: Stops texting the dispatcher entirely -> Restores one single source of truth

User Action: Relies solely on the app for the full shift, no parallel channel

Internal State: Professional ownership, the tool finally works the way he needs it to

Pain Point Addressed: Off-platform workaround of texting dispatcher instead of using the app (UXR-01)

## Competitive advantages
1. Real-time system of record: closes the data-integrity gap that texted updates and the dispatcher's stale dashboard both suffer from today.
2. Zero double-entry: eliminates the paper manifest entirely, recovering time the workaround was quietly costing every shift.
3. Scales across the 95%: a product fix reaches every driver at once, unlike a personal coping habit that only helps the one person who adopted it.
