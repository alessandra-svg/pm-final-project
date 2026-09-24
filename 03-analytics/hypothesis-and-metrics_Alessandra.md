# Data-Backed Hypothesis, Module 3

- **Scenario:** RouteLogic Velocity (B2B)  
- **Bet type:** Optimizing the existing

## The hypothesis

> Based on Coordinator interviews (UXR-02: "I reassign a route and the driver doesn't see it for ten to fifteen minutes"; "we keep a WhatsApp group as the real system"), with the same dashboard lag reported by a night-shift Dispatcher (UXR-09), confirmed by BUG-2044 (8 to 15 min reassignment delay) and BUG-2072 (20 to 60 min dashboard lag), plus a quant-only signal: Compliance Check averaging 14.6 min vs. a 3-min benchmark (CSAT 2.2), within a workflow where 69% of Coordinators don't reach Shift Handoff, we believe that solving dashboard reliability and Compliance Check efficiency for the Fleet Coordinator will result in Coordinators trusting the platform as their single source of truth and completing their daily workflow past Compliance, as measured by a 45–60% relative increase in workflow completion past Compliance Check, from 31% to 45–50% by the end of the pilot. We will protect Route Assignment completion rate, currently 71%, which must not drop and make a go/no-go decision after one full pilot cycle, matching the Velocity pilot cadence that produced the \+34% route-assign speed result.

## Evidence

- **Qualitative (M2):** Standing at a doorstep in the rain with a package in one hand, forced through three taps across three screens just to mark a delivery complete, while the "Start Route" button he uses 30 times a day sits buried under features he's never touched, to the point he's started texting his dispatcher instead of using the app at all.  
- **Quantitative (M3):** Coordinator interviews (UXR-02: "I reassign a route and the driver doesn't see it for ten to fifteen minutes"; "we keep a WhatsApp group as the real system"), with the same dashboard lag reported by a night-shift Dispatcher (UXR-09), confirmed by BUG-2044 (8 to 15 min reassignment delay) and BUG-2072 (20 to 60 min dashboard lag), plus a quant-only signal: Compliance Check averaging 14.6 min vs. a 3-min benchmark (CSAT 2.2), within a workflow where 69% of Coordinators don't reach Shift Handoff

## Persona & problem

- **Role:** the Coordinator  
- **Goal:** Assign routes, monitor drivers, and complete daily compliance/handoff tasks on a dashboard he can trust  
- **Friction:** Compliance Check logging takes 14.6 min vs. a 3-min benchmark, causing 69% of Coordinators to abandon the daily workflow at that step (CSAT 2.2, "Weak")  
- **Problem you are solving:** dashboard reliability and Compliance Check efficiency

## Outcome & metrics

- **Strategic outcome:** Coordinators trusting the platform as their single source of truth and completing their daily workflow past Compliance  
- **Primary success metric:** a 45–60% relative increase in workflow completion past Compliance Check, from 31% to 45–50% by the end of the pilot  
- **Guardrail metric:** Route Assignment completion rate, currently 71%, which must not drop  
- **Decision window:** one full pilot cycle, matching the Velocity pilot cadence that produced the \+34% route-assign speed result