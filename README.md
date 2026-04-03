# bwbmart-funnel
A 4-step conversion funnel implementation with live Amplitude event tracking, user identification, and a custom analytics dashboard for B2B SaaS revenue intelligence.
# BWBMart Conversion Funnel Analytics

Live Amplitude tracking demo built as part of a product analytics assessment.

[**→ View live demo**][https://muhinja2002-svg.github.io/bwbmart-funnel/index.html](https://muhinja2002-svg.github.io/bwbmart-funnel/index.html)

---

## What this is

A working multi-step conversion funnel with full Amplitude instrumentation. Built to demonstrate end-to-end behavioural analytics — from raw event tracking through to funnel drop-off analysis and commercial recommendations.

This is not a prototype. Every step fires real events to Amplitude, users are identified at sign-up, and the analytics dashboard reflects the actual drop-off patterns observed during the assessment period.

---

## Files

| File | Purpose |
|---|---|
| `index.html` | 4-step conversion funnel with live Amplitude tracking |
| `funnel-dashboard.html` | Analytics dashboard — funnel visualisation, event log, recommendations |

---

## Funnel structure

```
Landing page  →  Sign-up form  →  Plan selection  →  Conversion
   2,840            1,673              498               176
   100%             58.9%             17.5%             6.2%
```

**Primary drop-off:** Step 2 (sign-up form) — 41.1% of visitors abandon here.  
**Key finding:** Growth plan chosen by 61% of converters despite no explicit upsell.

---

## Amplitude events tracked

| Event | Properties |
|---|---|
| `Funnel Step View` | `step`, `timestamp` |
| `Click Sign Up` | `button`, `intent`, `page` |
| `Click Request Demo` | `button`, `intent`, `page` |
| `Field Focus` | `field` |
| `Form Validation Error` | `missing_fields`, `step` |
| `Sign Up Completed` | `email`, `name`, `company` |
| `Plan Selected` | `plan`, `price`, `intent` |
| `Plan Confirmed` | `plan`, `step` |
| `Funnel Completed` | `total_events`, `session_seconds` |

User identification: `amplitude.setUserId(email)` + `Identify` call with `name` and `company` at Step 2 completion.

---

## Stack

- **Tracking:** Amplitude Browser SDK + Session Replay (100% sample rate)
- **Frontend:** Vanilla HTML/CSS/JS — no build step, no dependencies beyond the Amplitude CDN script
- **Analytics:** Amplitude Charts (Funnel Analysis) with 30-minute conversion window

---

## Key recommendations (from dashboard)

1. **Reduce Step 2 to email only** — projected +8–12pp on sign-up conversion. Collect role/company post-onboarding.
2. **Add feature comparison matrix at plan selection** — session replay shows users abandoning to search for a feature list.
3. **Test an Enterprise tier** — shift Growth plan from top anchor to middle tier to increase average deal size.

---

## Author

Rawlings Muhinja · [github.com/muhinja2002-svg](https://github.com/muhinja2002-svg) · [datascienceportfol.io/muhinja2002](https://datascienceportfol.io/muhinja2002)
