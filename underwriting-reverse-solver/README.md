# Reverse Solver and Verified Workpapers

## What the feature does

The reverse solver starts with a property, desired outcomes, and underwriting limits. It works backward to produce candidate deal structures that may satisfy those requirements.

Typical inputs include target return, purchase-price limits, debt-service coverage, leverage, vacancy, rent growth, and exit assumptions.

## How to run it

1. Open **Underwriting** from the dashboard.
2. Open a workpaper you own or that has been shared with you.
3. Expand **Executive Verdict** and **Solver Workpaper**.
4. Open **Rerun options**.
5. Select **Generate again**.
6. Review the candidate results, blockers, assumptions, and evidence status.

Shared workpapers appear in the underwriting list only when you have active access. Being able to open a direct link does not automatically grant editing or approval permissions.

## Verified evidence status

When the workpaper shows **Signed bundle verified**, Orion has:

- stored the solver result and candidate set;
- linked the result to an immutable market snapshot;
- packaged the relevant execution evidence;
- digitally signed the package; and
- reloaded and verified the stored package.

This protects traceability and detects later tampering. It does not mean the deal is approved, the assumptions are correct, or the investment is suitable.

## If generation fails

The page provides a safe explanation and recommended next step when available. Common categories include missing immutable snapshot evidence, unresolved operating evidence, or unavailable signing configuration. Retry only after the stated issue has been corrected; contact support if the message persists.

## Synthetic staging evidence

Any evidence labeled **SYNTHETIC STAGING QA**, **NOT REAL**, or **NOT FOR PRODUCTION UNDERWRITING** is test data. It must never be interpreted as market evidence or used for a live investment decision.
