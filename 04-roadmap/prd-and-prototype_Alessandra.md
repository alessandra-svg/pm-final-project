# One-Click Compliance Checklist, Simplified PRD (RouteLogic)

**Author:** Me · **Status:** Draft · **Target:** High-Fidelity Prototype · **Persona:** Coordinator

## 1. The Big Picture
- **Vision:** To eliminate the manual re-typing that makes the Fleet Coordinator's Compliance Check take 14.6 minutes instead of 3, by pre-filling it with data RouteLogic already holds so Coordinators only review, fix exceptions and confirm.
- **Press release:** Today RouteLogic launches the One-Click Compliance Checklist for Coordinators. Compliance Check logging takes 14.6 minutes today, nearly 5× the 3-minute benchmark, and it is where the daily workflow loses 23 points: only 48% of Coordinators get past it, against 71% who complete Route Assignment. The new checklist opens pre-filled with vehicle, driver and route data from the step the Coordinator just finished.
Coordinators now review instead of retype. They confirm all pre-filled values in one action and fill in only the fields the system cannot know, which are highlighted. Every value shows when it was last updated, so Coordinators can trust what they confirm. The record is the same compliance record as today, with the same regulatory validity.
- **Success metric:** Workflow completion through Shift Handoff
- **Guardrail:** Route Assignment completion

## 2. The Details
### User stories
- 1. As a Coordinator, I want the checklist to open pre-filled and confirm it in one action, so that I finish compliance in minutes, not 14.6.
- ◦ All fields with existing system data are populated on load.
- ◦ With no empty required fields, one click on "Confirm all" submits the record.
- 2. As a Coordinator, I want to see immediately which fields need my input, so that I don't scan the whole form.
- ◦ Empty required fields are highlighted, and a counter shows how many remain.
- ◦ "Confirm all" stays disabled until the counter reaches 0.
- 3. As a Coordinator, I want to know how fresh each pre-filled value is, so that I can confirm it without cross-checking the WhatsApp group.
- ◦ Every pre-filled value shows its source and a "last updated" time.
- ◦ Values older than 15 min are flagged and must be confirmed one by one.
### Screens to build
- 1. Compliance queue (entry point) - Opens right after Route Assignment
- 2. Checklist (feature core) - Review and confirm one vehicle's check on a single screen
- 3. Confirmation (success) - Proves the record is saved and moves the Coordinator on
### Functional requirements
- FR1 - Pre-fill from existing data - 100% of fields with system data are populated on load - M1
- FR2- Confirm-all - 1 click submits when all required fields are filled and no flag is open - M2
- FR3 - Exception editing - Any pre-filled field is editable inline in 1 click; edited fields are tagged and logged - M2
- FR4- Empty-field highlighting - 100% of empty required fields are highlighted; the counter matches their number - M3
- FR5 - Same compliance record - The record holds the same fields as today's form, plus Coordinator ID and timestamp - M4
- FR6 - Step tracking preserved - Events compliance_started and compliance_submitted (with duration in seconds) fire once per check - M5
- FR7 - Input validation - Departure time accepts only a valid 24-hour time (HH:MM); expiry fields accept only a valid calendar date. Invalid values show an inline error, count as "need input", and keep "Confirm all" disabled - M4
### Smart behaviors (Situation → Outcome)
- IF all fields are pre-filled and updated ≤ 15 min ago, THEN "Confirm all" is enabled and is the primary action.
- IF one or more required fields are empty, THEN those fields are highlighted, the counter shows N, and "Confirm all" is disabled.
- IF a manually entered or edited value has an invalid format, THEN the field shows an inline error ("Use HH:MM, e.g. 06:30"), counts as a field needing input, and "Confirm all" stays disabled.
- IF a value was updated > 15 min ago (BUG-2072 lag), THEN an amber flag shows "Updated X min ago" and that field needs its own "Verify" before "Confirm all".
- IF a document expiry date is before today, THEN a red flag appears, the value is excluded from "Confirm all", and the Coordinator must mark Pass or Fail.
- IF the Coordinator edits a pre-filled value, THEN the field is tagged "Edited" and the edit is saved in the record.
- IF no system data loads for a vehicle, THEN a banner shows "Pre-fill unavailable, manual entry", all fields become manual, and the flow still completes.
- IF the check is submitted and the queue is empty, THEN the confirmation screen shows "Continue to Shift Handoff".
### Technical constraints
- • No external APIs and no AI calls: all data is a hardcoded mock JSON inside the prototype.
- • No login: the prototype opens as a single hardcoded Coordinator.
- • State in React useState only: no localStorage, no backend, no persistence between sessions.
- • Tracking events (FR6) are shown in an on-screen debug panel, not sent anywhere.
- • The 15-min stale rule uses mock "last updated" timestamps relative to the current time.

## 3. The Logistics
### Features out
- W1a AI suggestions for fields with no system data
- W1b Auto-submission
- W2 New integrations (telematics, third-party compliance)
- W3 Changes to the Route Assignment flow
- W4 Changes to which items the checklist requires
- W5 Mobile version (B4), audit PDF export (B9), driver notifications (B6)
- S2 Bulk confirm across vehicles
### Edge cases & safety guard
- Pre-filled value is stale (> 15 min). Safety guard: A stale value can never pass through "Confirm all"; its timestamp is saved in the record.
- Pre-filled value belongs to the wrong vehicle or driver. Safety guard: Pre-fill uses only records linked to the vehicle ID assigned in Route Assignment; on any ID mismatch the field stays empty.
- Document expired. Safety guard: An expired document is never recorded as Pass by default; Pass requires an explicit choice, which is logged.
- No data loads. Safety guard: Empty fields are never filled with placeholders or last-known values from other vehicles.
- Invalid date or time format. Safety guard: An invalid value is never saved in the record.
- Coordinator leaves mid-check. Safety guard: No partial record is saved or counted; compliance_submitted fires only on full submission.
- Double click on "Confirm all". Safety guard: The button is disabled after the first click; one record per vehicle per day.
### Decision log
- Pre-fill only from existing RouteLogic data
- No change to the Route Assignment flow
### Evals
- E1 – Accuracy. Target: ≥ 95% of pre-filled values confirmed without edit. Measured by: Share of fields tagged "Edited" per record.
- E2 – Time-on-task. Target: Median Compliance Check time ≤ 5 min (from 14.6), stretch 3 min. Measured by: Duration in compliance_submitted.
- E3 – Safety triggers. Target: 100% of values > 15 min flagged; 0 expired documents submitted as Pass without explicit action; 0 records submitted without a Coordinator action. Measured by: Prototype test script on the mock dataset, then pilot logs.

## MoSCoW scope
- **Must:** M1 – Pre-fill from existing RouteLogic data. Every checklist field that the system already holds (e.g., vehicle, driver, route from the preceding Route Assignment step) is populated automatically. This is the core of the time reduction.; M2 – Confirm-all with exception editing. The Coordinator confirms all pre-filled values in one action and edits only the fields that are wrong or empty. Without it, pre-fill still forces field-by-field review.; M3 – Empty-field highlighting. Fields with no system data are clearly marked for manual entry, so the Coordinator doesn't have to scan the whole form to find what's missing.; M4 – Same compliance record as today. The submission produces the same record, with the same regulatory validity, as the current flow. Without it the Coordinator cannot use the feature at all.; M5 – Preserve existing step tracking. The new flow fires the same step-completion and time-on-task events as today. Without them the primary metric and the go/no-go break.
- **Should:** S1 – "Last updated" timestamp on pre-filled values. BUG-2072 causes 20–60 min of dashboard lag, so pre-filled data may be stale. Without a timestamp, Coordinators may fall back to re-verifying every field.; S2 – Bulk confirm across vehicles. If the Coordinator logs one checklist per vehicle, this multiplies the time saving. Include only if it fits in Effort 2.
- **Could:** C1 – Save and resume draft. Useful if interruptions drive abandonment, but there's no evidence of that yet.; C2 – Remember last-used values for fields with no system data.; C3 – Keyboard shortcuts and inline validation hints.
- **Won't (now):** W1a – AI suggestions for fields with no system data. Won't now. V2 candidate if the pilot shows that manual fields remain the main time cost; the Coordinator still confirms every value.; W1b – Auto-submission. Won't, regardless of opt-in, until Compliance/Legal confirms that a record without human confirmation is valid.; W2 – New integrations (telematics, third-party compliance systems).; W3 – Changes to the Route Assignment flow. This protects the 71% guardrail.; W4 – Changes to which items the checklist requires. That's a regulatory decision, not a UX one.; W5 – Mobile version (B4, cut), audit PDF export (B9, Later), driver notifications (B6, Later).

---
**Builder hook:** Build a working prototype based on this PRD. Use the User Story as the core flow, Functional Requirements as build constraints, and prioritize speed and clarity over visual complexity.
