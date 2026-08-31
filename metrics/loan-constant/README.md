# Loan Constant

The loan constant expresses annual scheduled debt service as a percentage of the original loan principal.

## Formula

```text
Loan Constant = Annual Debt Service / Original Loan Amount
```

For a fully amortizing fixed-rate loan, the payment is determined by interest rate, amortization period, and payment frequency.

## Inputs and conventions

- Annual debt service includes scheduled principal and interest.
- Use original principal unless a current-balance convention is explicitly stated.
- Interest-only periods, rate resets, balloon payments, and fees require separate disclosure.

## Interpretation

A `7%` loan constant means scheduled annual principal and interest equal 7% of original principal. Comparing the loan constant with the property's cap rate can help frame leverage effects, but it is not a complete return analysis.

## Worked example

For `$350,000` of annual debt service on a `$5,000,000` original loan:

```text
$350,000 / $5,000,000 = 7.0%
```

## Limitations and checks

- The metric does not show maturity risk, balloon size, covenants, or floating-rate exposure.
- Two loans can share a constant while having different term and risk profiles.
- Review the full amortization schedule, DSCR, debt yield, rate caps, and maturity date.

[Back to metric index](../README.md)
