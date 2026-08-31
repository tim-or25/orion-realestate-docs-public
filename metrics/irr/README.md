# Internal Rate of Return (IRR)

IRR is the annualized discount rate that makes the net present value of an investment's complete equity cash-flow stream equal to zero.

## Formula

```text
0 = Σ [CF_t / (1 + IRR)^t]
```

`CF_t` is the net equity cash flow at time `t`. The stream normally begins with negative acquisition equity, includes interim distributions or contributions, and ends with net sale proceeds. Because IRR is solved iteratively, it is not calculated by a simple average.

## Inputs and conventions

- Initial equity includes acquisition cash and any modeled closing or initial capital costs.
- Interim cash flows must use consistent monthly, quarterly, or annual dates.
- Sale proceeds should be net of disposition costs, debt payoff, and other modeled closing items.
- A periodic solution must be annualized consistently. Irregularly dated cash flows require a date-aware method.

## Interpretation

IRR combines timing and magnitude: earlier distributions generally increase IRR. Compare it against the investor's required return and against scenarios using the same hold and timing conventions. A high IRR can still accompany a modest total profit or aggressive exit assumptions.

## Worked example

An investor contributes `$1,000,000`, receives `$80,000` at each of years 1–4, and receives `$1,280,000` in year 5. The IRR is the rate that discounts those inflows back to `$1,000,000`; it is approximately `10%`.

## Limitations and checks

- Multiple sign changes can create multiple mathematical IRRs or no useful solution.
- IRR assumes reinvestment at the calculated rate and can overstate the appeal of short holds.
- Always review equity multiple, absolute profit, hold period, exit cap rate, and the underlying cash-flow schedule alongside IRR.

[Back to metric index](../README.md)
