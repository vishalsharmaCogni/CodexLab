# Personalized Payment Reminders — Concept v1.0

**Concept ID:** payment-reminders  
**Status:** Proposed for manager review; not approved  
**Version:** 1.0  
**Owner:** Product Owner (to confirm)  
**Assigned PM / Reviewer:** To be assigned  
**Date:** 2026-10-28

## Problem and users
Credit cardholders may not receive payment reminders at their preferred times or through their preferred channels. This can contribute to overlooked reminders and notification fatigue. The actual prevalence and impact require validation.

**Users:** Cardholders managing one or more credit card accounts through digital servicing experiences.

**Desired outcome:** Help cardholders plan timely payments by allowing them to manage reminder timing and delivery channels.

## Market context (publicly shareable)
Major issuers including Chase, Capital One, and American Express publicly describe payment or account alerts and notification preferences. The exact channels, timing options, and eligibility vary by issuer and market. References:
- Chase account alerts: https://www.chase.com/personal/mobile-online-banking/login-alerts
- Capital One late payment support: https://www.capitalone.com/help-center/credit-cards/late-payment-support/
- American Express account alerts: https://www.americanexpress.com/sg/security/safety-fraud/how-amex-protects-you/fraud-account-alerts/

These are directional market examples, not verified feature-by-feature equivalence.

## Options considered
| Option | Benefits | Trade-offs |
|---|---|---|
| A. Channel choice | Simple configuration and potential fast delivery | Limited control over reminder timing |
| B. Timing and channel choice | Meaningful self-service flexibility | Requires reliable scheduling, delivery and preference persistence |
| C. Intelligent reminders | Potentially more contextually relevant | Greater data, model governance and operational complexity |

**Recommendation:** Option B, with rules-based payment awareness, subject to feasibility and compliance review.

## Proposed experience and requirements
- **REQ-001:** Eligible cardholders can choose reminder timing (proposed: 1, 3 or 7 days before payment due date).
- **REQ-002:** Eligible cardholders can choose available channels (proposed: push, email and SMS), subject to permissions and applicable consent.
- **REQ-003:** Cardholders can view, change and persist their preferences in supported digital experiences.
- **REQ-004:** Reminder orchestration checks payment status and applies validated rules to avoid misleading reminders after payment or when Autopay is scheduled.
- **REQ-005:** The system maintains auditable preference changes and respects applicable mandatory-servicing-message rules.
- **REQ-006:** Settings and notifications meet accessibility and security requirements.
- **REQ-007:** Provide appropriate defaults, delivery-error handling, and account-level preference behavior for multi-account users.

## MVP boundaries
**In scope for feasibility assessment:** timing choices, channel preferences, preference persistence, payment-aware suppression, consent controls, accessibility, instrumentation.

**Out of scope initially:** predictive/AI-based timing, personalized delinquency interventions, complex cross-channel optimization, and arbitrary user-defined schedules.

## Success measures (proposed; targets and baselines not yet established)
- **Primary:** missed-payment rate for eligible enrolled cardholders compared with a suitable control group.
- **Secondary:** enrollment, on-time payment rate, notification delivery success, preference changes and opt-outs.
- **Guardrails:** incorrect/duplicate reminders, complaints, operational costs and compliance exceptions.

## Assumptions and dependencies
- Existing systems can provide sufficiently timely due-date, payment and Autopay signals; **unverified**.
- Delivery providers and channels can support the selected timing; **unverified**.
- Customer research will establish meaningful demand for customization; **unverified**.
- Legal and Compliance will determine channel-specific consent, required communications, quiet hours, and retention obligations.

## Risks and mitigations
| Risk | Proposed mitigation |
|---|---|
| Reminder after payment | Check current payment status and establish suppression windows |
| Conflicting account preferences | Define account-specific vs shared preference ownership |
| Consent or mandatory-notice conflicts | Review with Legal and Compliance before pilot |
| Excessive reminders | Frequency caps and user-visible defaults |
| Unproven business benefit | User research followed by controlled pilot |

## Discovery and validation plan
1. Interview cardholders about reminder needs, timing and preferred channels.
2. Inventory current alerts, preferences, payment events, and notification services.
3. Validate compliance and accessibility requirements.
4. Prototype the settings journey and test comprehension.
5. Pilot with eligible users and measure outcomes against a control group.

## Manager review request
**Requested decision:** Approve further discovery and solution design, request changes, or decline. Approval here is not production release authorization.

**Review state:** Pending authenticated manager review of this exact version.

## Version history
- **v1.0 (2026-10-28):** Initial sanitized concept for public-repository review. No confidential internal source content included.
