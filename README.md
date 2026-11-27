# FeeSpec Open Data (2026)

Open CSV datasets modeling 2026 US marketplace seller payouts across 8 platforms, eBay's hidden sales-tax Final Value Fee effect across all 50 states plus DC, and payment processing fees from $5 to $10,000 across Stripe, PayPal, and Square.

All figures are computed from published 2026 fee schedules and Tax Foundation state/local sales tax tables. Interactive calculators and full methodology live at [feespec.com](https://feespec.com/).

## Datasets in this repository

| File | Coverage | Live report & calculator |
|---|---|---|
| [`data/marketplace-seller-fees-2026-2027.csv`](data/marketplace-seller-fees-2026-2027.csv) | 8 sale prices ($15 to $2,000) across PayPal G&S, Depop US, TikTok Shop, Etsy, Mercari, Whatnot, eBay Basic Store, eBay Standard, and Poshmark | [Marketplace Seller Fees Report](https://feespec.com/reports/marketplace-seller-fees-2026-2027/) / [Fee Comparator](https://feespec.com/) |
| [`data/ebay-hidden-sales-tax-fee.csv`](data/ebay-hidden-sales-tax-fee.csv) | All 50 US states + DC: combined sales tax rate, effective eBay FVF on item price, and extra fee per $100 and $500 sale | [eBay Hidden Sales Tax Fee Report](https://feespec.com/reports/ebay-hidden-sales-tax-fee/) / [eBay Fee Calculator](https://feespec.com/ebay-fee-calculator/) |
| [`data/payment-processing-cost-index.csv`](data/payment-processing-cost-index.csv) | 12 invoice tiers ($5 to $10,000) comparing Stripe card, Stripe ACH ($5 cap), Stripe Terminal, PayPal Standard, PayPal G&S, and Square online/in-person | [Payment Processing Cost Index](https://feespec.com/reports/payment-processing-cost-index/) / [Stripe Fee Calculator](https://feespec.com/stripe-fee-calculator/) |

---

## 1. Marketplace Seller Payout Spread (2026)

Key findings from [`data/marketplace-seller-fees-2026-2027.csv`](data/marketplace-seller-fees-2026-2027.csv):
- On a **$100** sale, seller net payout spans **$16.52** between PayPal G&S ($96.52) and Poshmark ($80.00).
- On a **$500** sale, the gap widens to **$84.56** ($484.56 on PayPal G&S and $481.81 on Depop US vs. $426.48 on eBay Standard and $400.00 on Poshmark).
- On a **$1,000** sale, choosing the platform changes seller payout by **$169.61** ($969.61 vs. $800.00). At **$2,000**, the spread reaches **$339.71**.
- A Basic Store subscription (12.7% Final Value Fee up to $2,500 instead of 13.6%) adds **$0.96** to the eBay payout on a $100 sale and **$19.35** on a $2,000 sale, before the monthly store fee.

| Sale price | PayPal G&S | Depop US | TikTok Shop | Etsy US | Mercari US | Whatnot US | eBay Basic Store | eBay Std | Poshmark US | Payout spread |
|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| $15 | $14.06 | $14.02 | $14.10 | $13.09 | $13.50 | $13.03 | $12.55 | $12.41 | $12.00 | $2.10 |
| $25 | $23.76 | $23.66 | $23.50 | $22.11 | $22.50 | $21.92 | $21.19 | $20.94 | $20.00 | $3.76 |
| $50 | $48.01 | $47.78 | $47.00 | $44.69 | $45.00 | $44.14 | $42.77 | $42.29 | $40.00 | $8.01 |
| $100 | $96.52 | $96.00 | $94.00 | $89.82 | $90.00 | $88.58 | $85.94 | $84.98 | $80.00 | $16.52 |
| $250 | $242.03 | $240.68 | $235.00 | $225.24 | $225.00 | $221.90 | $215.46 | $213.04 | $200.00 | $42.03 |
| $500 | $484.56 | $481.81 | $470.00 | $450.92 | $450.00 | $444.11 | $431.32 | $426.48 | $400.00 | $84.56 |
| $1,000 | $969.61 | $964.07 | $940.00 | $902.29 | $900.00 | $888.52 | $863.04 | $853.36 | $800.00 | $169.61 |
| $2,000 | $1,939.71 | $1,928.58 | $1,880.00 | $1,805.03 | $1,800.00 | $1,777.33 | $1,726.47 | $1,707.12 | $1,600.00 | $339.71 |

---

## 2. eBay's Hidden Sales-Tax Fee Across 50 States + DC

Because eBay calculates its 13.60% standard Final Value Fee on the buyer's total payment including collected state and local sales tax, a seller's effective fee depends on where the buyer lives:
- **Zero-tax states (DE, MT, NH, OR):** effective FVF stays at **13.60%** ($68.40 total fee on a $500 order).
- **Louisiana (10.11% avg combined tax):** effective FVF rises to **14.97%**, adding **$6.87** per $500 sale ($75.27 total).
- **Tennessee (9.61%), Washington (9.51%), Alabama and Arkansas (9.46%):** effective FVF reaches **14.89% to 14.91%** (+$6.43 to +$6.53 per $500 sale).
- **California (8.99%) & Illinois (8.96%):** effective FVF hits **14.82%** (+$6.11 and +$6.09 per $500 sale).

Full 51-row table (50 states + DC) is in [`data/ebay-hidden-sales-tax-fee.csv`](data/ebay-hidden-sales-tax-fee.csv).

---

## 3. Payment Processing Cost Index ($5 to $10,000)

Key findings from [`data/payment-processing-cost-index.csv`](data/payment-processing-cost-index.csv):
- **Small tickets ($5–$10):** fixed per-transaction fees push PayPal Standard to **13.20%** ($0.66 on $5) and Stripe online card to **9.00%** ($0.45 on $5).
- **B2B invoices ($625+):** Stripe ACH Direct Debit caps at **$5.00** (0.80% below $625). On a **$1,000** invoice, ACH saves **$24.30** vs. Stripe card ($29.30) and **$30.39** vs. PayPal Standard ($35.39).
- **High-ticket invoices ($10,000):** Stripe ACH costs **$5.00** (0.05%) vs. **$290.30** on Stripe card ($285.30 saved) and **$349.49** on PayPal Standard ($344.49 saved).

---

## Primary Official Sources

- eBay: [Selling fees](https://www.ebay.com/help/selling/fees-credits-invoices/selling-fees?id=4822) and [Store selling fees](https://www.ebay.com/help/selling/fees-credits-invoices/store-selling-fees?id=4809)
- PayPal: [US Merchant Fees](https://www.paypal.com/us/legal/merchant-fees-full)
- Stripe: [Standard US Pricing](https://stripe.com/pricing)
- Square: [US Pricing](https://squareup.com/us/en/pricing)
- Etsy: [Fees & Payments Policy](https://www.etsy.com/legal/fees/)
- Depop: [US Fees](https://depophelp.zendesk.com/hc/en-gb/sections/360001963478-Fees-and-charges) · Poshmark: [Seller Fees](https://support.poshmark.com/s/article/What-are-the-fees-for-selling-on-Poshmark?language=en_US) · Mercari: [Fee Schedule](https://www.mercari.com/us/help_center/topics/fees/) · Whatnot: [Seller Fees](https://help.whatnot.com/hc/en-us/articles/4410508007565-Whatnot-Seller-Fees) · TikTok Shop: [US Commission](https://seller-us.tiktok.com/university/essay?knowledge_id=6837860260726529)
- Tax Foundation: [State and Local Sales Tax Rates](https://taxfoundation.org/data/all/state/sales-tax-rates/)

## Interactive Calculators and Embeds

- Fee comparator & calculators: https://feespec.com/
- eBay fee calculator: https://feespec.com/ebay-fee-calculator/
- PayPal fee calculator: https://feespec.com/paypal-fee-calculator/
- Stripe fee calculator: https://feespec.com/stripe-fee-calculator/
- Etsy, Poshmark, Mercari, Depop, Whatnot, TikTok Shop, Square, Copart calculators: https://feespec.com/
- Lightweight iframe embeds (no sign-up): `https://feespec.com/embed/ebay/`, `https://feespec.com/embed/paypal/`, `https://feespec.com/embed/stripe/`

## License and Citation

Licensed under [CC-BY-4.0](LICENSE). Citation metadata is in [`CITATION.cff`](CITATION.cff).

```text
FeeSpec (2026). FeeSpec Open Data 2026: US Marketplace Seller Fees, eBay Sales-Tax FVF Impact, and Payment Processing Cost Index [Dataset]. https://feespec.com/reports/ (CC-BY-4.0).
```
