# Feature Roadmap, Module 4 · RouteLogic Velocity

**Team:** 2 engineers + 1 designer + 1 CS lead

## Strategic anchors
- **Persona:** Coordinator
- **Primary metric:** a 45–60% relative increase in workflow completion past Compliance Check, from 31% to 45–50% by the end of the pilot
- **Moment of misery:** Compliance Check logging takes 14.6 min vs. a 3-min benchmark, causing 69% of Coordinators to abandon the daily workflow at that step (CSAT 2.2, "Weak")
- **Guardrail:** Route Assignment completion rate, currently 71%, which must not drop

## Scoring
| Feature | Value | Effort | Quadrant | Decision | Rationale |
|---|---|---|---|---|---|
| B1 One-Click Compliance Checklist | 5 | 2 | Quick Win | Now | Largest absolute drop in the funnel (−23 pts, 32% relative) and a 5× time gap (14.6 vs. 3 min). Effort 2 holds only with scope limited to pre-fill from existing data. Ships alongside a parallel bug-fix track (BUG-2044, BUG-2072; effort TBD pending a root-cause spike), which is required to test the dashboard-reliability half of the hypothesis. |
| B2 Smart Daily Report Auto-Fill | 2 | 4 | Time Sinker | Later | Highest relative drop (42%), but it sits downstream of the primary metric and carries AI accuracy risk. |
| B3 Shift Handoff Wizard | 4 | 3 | Major Project | Next | Handoff loses 35% of arrivals and sits right before the metric. It's the first lever if the pilot stalls around 40%, i.e. if the bug fixes don't lift Route Assignment conversion enough to reach 45–50%. |
| B4 Mobile-First Coordinator Dashboard | 3 | 5 | Time Sinker | Cut | Not feasible in 4 weeks, a redesign of dispatch puts the guardrail at risk, and there's no evidence Coordinators work primarily on mobile. |
| B5 Step Progress Indicator | 2 | 1 | Fill-In | Next | Cheap, but step-level funnel data already exists, and nothing shows that disorientation drives abandonment. Pull into Now only if there's slack. |
| B6 Driver Alert Notifications | 3 | 3 | Time Sinker | Later | Depends on BUG-2044's root cause, which is being fixed in parallel with B1. If the delay lies in delivery, it merges into that fix. |
| B7 Contextual AI ETA Display | 1 | 3 | Time Sinker | Cut | Adoption of an AI feature is an Engineering/Sales goal, not Coordinator friction. |
| B8 Fleet Analytics Manager View | 1 | 4 | Time Sinker | Cut | Serves the executive buyer, which is the pattern Velocity exists to break. |
| B9 Compliance Audit Trail Export | 2 | 2 | Fill-In | Later | Compliance-adjacent but downstream of logging time. It becomes cheap after B1 structures the data. |
| B10 In-App Coordinator Training | 2 | 2 | Fill-In | Later | The friction is structural, not a skill gap. The CS lead covers pilot onboarding manually; revisit when scaling beyond 3 accounts. |

## Roadmap
### NOW, Pilot (4 weeks, 3 accounts)
- **B1 One-Click Compliance Checklist**, Largest absolute drop in the funnel (−23 pts, 32% relative) and a 5× time gap (14.6 vs. 3 min). Effort 2 holds only with scope limited to pre-fill from existing data. Ships alongside a parallel bug-fix track (BUG-2044, BUG-2072; effort TBD pending a root-cause spike), which is required to test the dashboard-reliability half of the hypothesis.

### NEXT, GA Release (weeks 5-8)
- **B3 Shift Handoff Wizard**, Handoff loses 35% of arrivals and sits right before the metric. It's the first lever if the pilot stalls around 40%, i.e. if the bug fixes don't lift Route Assignment conversion enough to reach 45–50%.
- **B5 Step Progress Indicator**, Cheap, but step-level funnel data already exists, and nothing shows that disorientation drives abandonment. Pull into Now only if there's slack.

### LATER, backlog
- **B2 Smart Daily Report Auto-Fill**, Highest relative drop (42%), but it sits downstream of the primary metric and carries AI accuracy risk.
- **B6 Driver Alert Notifications**, Depends on BUG-2044's root cause, which is being fixed in parallel with B1. If the delay lies in delivery, it merges into that fix.
- **B9 Compliance Audit Trail Export**, Compliance-adjacent but downstream of logging time. It becomes cheap after B1 structures the data.
- **B10 In-App Coordinator Training**, The friction is structural, not a skill gap. The CS lead covers pilot onboarding manually; revisit when scaling beyond 3 accounts.

### ✂ Cut List
- **B4 Mobile-First Coordinator Dashboard**, Not feasible in 4 weeks, a redesign of dispatch puts the guardrail at risk, and there's no evidence Coordinators work primarily on mobile.
- **B7 Contextual AI ETA Display**, Adoption of an AI feature is an Engineering/Sales goal, not Coordinator friction.
- **B8 Fleet Analytics Manager View**, Serves the executive buyer, which is the pattern Velocity exists to break.
