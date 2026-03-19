# PRD: Boostly ROI Calculator

## Goal
Give skeptical restaurant owners a personalized number — "here's what Boostly would make you" — before they hit the pricing page. Remove the "$597/month, is it worth it?" friction by showing the math with their own inputs.

---

## Target User
The Boostly persona: independent restaurant owner, 1–3 locations, skeptical of marketing tools, responds to concrete ROI. They've been burned by Yelp ads and boosted posts that didn't track. They need to see their specific numbers, not averages.

---

## Inputs

| Input | Label | Default | Range |
|---|---|---|---|
| Weekly covers | "How many guests do you serve per week?" | 300 | 50–2,000 |
| Average ticket size | "What's your average spend per guest?" | $22 | $8–$150 |
| Current repeat rate | "What % of guests come back within 90 days?" | 20% | 5–60% |
| Boostly plan | "Which plan are you considering?" | Growth ($597) | Starter ($297) / Growth ($597) |

---

## Calculations & Assumptions

All assumptions sourced from Boostly platform data shown on the landing page.

### List Building
- **Opt-in rate:** 34% of weekly covers tap/scan and join the list
- **Monthly new contacts:** weekly covers × 4.33 × 34%

### Repeat Visit Uplift
- **Boostly repeat visit increase:** 68% uplift on current repeat rate
- **Additional monthly repeat visits:** (monthly guests × current repeat rate × 68%)
- **Revenue from additional repeats:** additional visits × avg ticket

### Campaign Revenue (1 slow-night campaign/month)
- **Campaign send size:** total list after 3 months (monthly new contacts × 3)
- **Campaign conversion rate:** 10% of recipients come in
- **Average campaign guests:** campaign list × 10%
- **Campaign revenue:** campaign guests × avg ticket

### Total Monthly Impact
```
additional_repeat_revenue = monthly_guests × repeat_rate × 0.68 × avg_ticket
campaign_revenue = (monthly_new_contacts × 3) × 0.10 × avg_ticket
total_monthly_revenue = additional_repeat_revenue + campaign_revenue
net_monthly_roi = total_monthly_revenue - plan_cost
annual_roi = net_monthly_roi × 12
payback_days = plan_cost / (total_monthly_revenue / 30)
```

---

## Outputs

Show four result cards, updating live as the user changes inputs:

1. **Additional Monthly Revenue** — total_monthly_revenue (large, prominent)
2. **Net Monthly ROI** — after Boostly cost
3. **Annual Return** — annual_roi
4. **Payback Period** — "You make back the monthly cost in X days"

Below results: a plain-English summary line:
> "Based on 300 weekly covers at $22/ticket, Boostly would generate an estimated $3,840/month in additional revenue — a 6.4× return on your $597 investment."

---

## Design
- Match index.html exactly: white background, purple (#7C3AED) accent, same nav/footer
- Inputs on the left, results on the right (two-column on desktop, stacked on mobile)
- Results update live on input change (no submit button needed)
- Slider + number input for each field (either works)
- Results highlighted in purple, large font — make the number the hero
- Disclaimer at bottom: "Estimates based on average results across 2,400+ Boostly restaurants. Individual results vary."
- CTA below results: "Start Your Free Trial →" linking to signup

---

## Out of Scope
- No user accounts or saved results
- No email capture on the calculator page
- No POS integration or real data import
- No comparison to competitors
