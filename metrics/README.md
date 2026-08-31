# Metrics and KPI Reference

This library explains the financial, debt, operating, valuation, and risk metrics shown in Orion Rigel. Each guide defines the metric, formula, required inputs, timing convention, interpretation, limitations, and a worked example.

## Metric library

| Metric | Primary question | Guide |
|---|---|---|
| Internal Rate of Return (IRR) | What annualized return is implied by the full equity cash-flow stream? | [IRR](./irr/README.md) |
| Capitalization Rate | What unlevered income yield does the property produce at a stated value? | [Cap Rate](./cap-rate/README.md) |
| Cash-on-Cash Return | What current-period cash yield is earned on invested equity? | [Cash-on-Cash](./cash-on-cash/README.md) |
| Debt Service Coverage Ratio | How comfortably does NOI cover scheduled debt service? | [DSCR](./dscr/README.md) |
| Loan-to-Value Ratio | How much of the property's value is financed with debt? | [LTV](./ltv/README.md) |
| Occupancy Break-even | What occupancy is required to cover operating expenses and debt service? | [Occupancy Break-even](./occupancy-break-even/README.md) |
| Debt Yield | What NOI yield does the lender receive on its loan basis? | [Debt Yield](./debt-yield/README.md) |
| Loan Constant | What annual debt-service burden does each dollar of original principal create? | [Loan Constant](./loan-constant/README.md) |
| Payback Period | How long until cumulative distributions recover invested capital? | [Payback Period](./payback-period/README.md) |
| Gross Rent Multiplier | How many years of gross rent are represented by the purchase price? | [GRM](./gross-rent-multiplier/README.md) |
| Net Operating Income | What income remains after property operating expenses but before financing and income taxes? | [NOI](./noi/README.md) |
| Return on Investment | What simple cumulative profit was earned relative to invested capital? | [ROI](./roi/README.md) |
| Vacancy Rate | What share of rentable inventory or potential rent is unoccupied or uncollected? | [Vacancy Rate](./vacancy-rate/README.md) |

## Reading rules

- Compare metrics only when valuation date, hold period, cash-flow timing, leverage, and expense definitions are consistent.
- A ratio is not a conclusion. Review its inputs, evidence date, source, and scenario before relying on it.
- Illustrative ranges are context-dependent. Market, asset class, property condition, loan structure, and investment mandate can materially change an acceptable result.
- Percentage outputs are displayed as percentages, while ratios such as DSCR and GRM are displayed as multiples.
- Forecast metrics are scenario outputs, not promises or investment advice.

## Public documentation boundary

These pages disclose standard industry formulas and Orion Rigel's user-facing conventions. They do not disclose private customer data, proprietary search logic, internal validation thresholds, or non-public benchmark values.

## Maintenance

Update the applicable metric page whenever a displayed formula, input definition, time convention, or public interpretation changes. Keep this index aligned with the KPI Reference Guide in the application.
