A/B Experiment Brief, RouteLogic (B2B)

Parameters
Parameter	Decision
Feature under test	One-Click Compliance Checklist
Persona	Coordinator
Expected outcome	Coordinators trusting the platform as their single source of truth and completing their daily workflow past Compliance
Primary success metric	workflow completion past Compliance Check
Baseline rate	Compliance Check averaging 14.6 min vs. a 3-min benchmark (CSAT 2.2), within a workflow where 69% of Coordinators don't reach Shift Handoff
Guardrail metric	Route Assignment completion rate (~71% baseline)
Guardrail boundary	a level below 66% at any point during the 4-week test and
Second guardrail	·
Minimum Detectable Effect	+14
Sample size per arm	188
Traffic split	50/50
Test duration	4 weeks
Significance threshold	p < 0.05, two-sided

Control vs. Variant
- Control (A): Compliance Check logging takes 14.6 minutes today, nearly 5× the 3-minute benchmark. Only 48% of Coordinators get past this step, against 71% who complete Route Assignment — a 23-point drop concentrated at Compliance Check (CSAT 2.2, "Weak").
- Variant (B): The Compliance Check opens pre-filled with data RouteLogic already holds, instead of empty; the Coordinator reviews and confirms in one action.

Screen 1 (Compliance queue): vehicle list with driver and route; status per vehicle (Ready to confirm / Needs input / Flagged); count of fields needing input per vehicle; "Start check" button per row.

Screen 2 (Checklist, feature core): pre-filled fields with source and "last updated" tag; highlighted empty fields; amber stale flag with "Verify" toggle; red flag on expired documents with Pass/Fail choice; inline edit with "Edited" tag; counter "N fields need input"; "Confirm all" button; running timer.

Screen 3 (Confirmation): record ID and timestamp; summary of values (edited and failed items highlighted); time taken vs. 3-min benchmark; "Next vehicle" / "Continue to Shift Handoff" button.

FR1: 100% of fields with system data are populated on load. 
FR2: 1 click submits when all required fields are filled and no flag is open.
- Held constant (isolation check): Route Assignment flow — unchanged (W3, D2: protects the 71% guardrail) 
- The compliance record — same regulatory fields as today, same validity (FR5) 
- Tracking/events — same existing schema, only duration added (FR6) 
- No AI, no new external integrations, no login (Technical Constraints, W2) 
- Onboarding, notifications, recommendation engine — out of scope, not mentioned in the PRD, identical in both arms 
- This variant bundles three separable mechanisms — pre-fill (FR1), single-click confirmation (FR2), and queue-level triage (Screen 1). The pilot measures their combined effect; it cannot isolate which mechanism drives any observed change. A follow-up test would be needed to attribute the effect to a single component.

Hypothesis
I believe that One-Click Compliance Checklist for Coordinator will result in Coordinators trusting the platform as their single source of truth and completing their daily workflow past Compliance, as measured by a +14 change in workflow completion past Compliance Check within 4 weeks. We will protect Route Assignment completion rate (~71% baseline) throughout the test.

Shipping criteria
We will ship if workflow completion past Compliance Check improves by ≥ +14 at p < 0.05, two-sided and Route Assignment completion rate (~71% baseline) does not reach a level below 66% at any point during the 4-week test and after 4 weeks. 
We will iterate if direction is positive but lift is below the MDE. 
We will kill if the primary metric shows no improvement or moves negatively. 
The read date is fixed at the end of 4 weeks, no results reviewed before this date.
