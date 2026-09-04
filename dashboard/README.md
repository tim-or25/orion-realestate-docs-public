# BORB Decision Center and Welcome

## ✨ At A Glance

Public guide to the BORB Decision Center and Welcome page as the main navigation, decision-readiness, and workflow surfaces for Orion Rigel users.

## 🎨 Reader Promise

> This page should make the dashboard feel like a control room, not a maze: where to start, where to go next, and what each surface is for.

## 🧭 How To Use This README

- Use this README to explain dashboard navigation, common actions, and first steps for new users.
- Keep guidance tied to what users can see and do in the product.
- Link out to topic-specific READMEs when a workflow goes deeper than dashboard orientation.

The BORB workspace has two complementary entry points:

- **Welcome** helps you create underwriting context or resume the single highest-priority task.
- **Decision Center** explains which underwriting decisions require attention, why they require attention, and what action clears them.

These pages are intentionally visually restrained. Their primary purpose is decision clarity, not displaying the maximum possible number of charts.

## 🐝 Welcome

Welcome changes according to your current underwriting state:

- With no underwriting work, it recommends creating underwriting context.
- With active exceptions, it identifies the highest-priority decision and provides a direct resume action.
- With no immediate queue pressure, it reports that underwriting decisions are current.

Only one action is labeled **Recommended next step**. Other cards remain available as navigation choices but are not presented as BORB recommendations.

**Continue Underwriting** resumes BORB's recommended decision. **Browse Underwriting Queue** opens all existing underwriting work. **Workspace History** contains existing underwriting, upload, and saved-scenario entry points.

## 🧭 Decision Center

The Decision Center is designed to answer:

> What requires attention, why does it matter, and what decision is currently prevented?

The top decision includes its priority, materiality, age, owner, selection rationale, and required action. Decision, refresh, and promotion queues remain separate because they represent different work:

- **Decision/review:** human judgment or candidate selection is required.
- **Refresh:** assumptions, calculations, or a promoted scenario may no longer be current.
- **Promotion:** work has cleared earlier gates and is ready for an advancement decision.

## 🚦 Decision Readiness and Exceptions

A Decision Record is evaluated for each underwriting item. It can identify:

- whether the item is ready, requires review, requires refresh, or is not ready;
- the exception and its severity;
- the conclusion, reliance, promotion, or approval that the exception prevents;
- the action required to resolve it;
- the owner, reviewer, approval authority, approval status, frozen model version, and review dates when available.

Missing governance is not silently treated as approval. An otherwise promotion-ready item remains blocked if its required frozen model version or approval-authority decision is missing.

BORB preserves each materially different Decision Record as a numbered, immutable version. If readiness, blockers, trust, model references, freshness, or governance changes, the prior record remains in history and the new record identifies the version it supersedes. Reloading an unchanged decision does not create a duplicate version.

This history becomes active after the corresponding database migration is applied. Before migration, BORB keeps the dashboard available using the current projection rather than presenting an unverified persistence claim.

## 📊 KPI Intelligence

Dashboard KPI commentary is deterministic and policy-relative. Each material metric answers **“relative to what?”** by showing:

- the governing policy floor and target;
- the portfolio average and distance above or below the floor;
- the number and percentage of scenarios that pass;
- the observed scenario range;
- the weakest scenario's remediation gap when failures exist;
- the policy version used to reach the conclusion.

The dashboard does not use free-form AI judgment to assign these KPI conclusions.

## 🔎 Trust and Provenance

Each material KPI displays one lineage state:

- **Verified lineage:** every observed scenario is source-linked and validated.
- **Partial lineage:** some, but not all, observed scenarios have source or validation links.
- **Unverified lineage:** no qualifying lineage is available.

Use the metric's information icon to review source-linked and validated scenario counts, average trust score, latest validation date, and the material inputs supporting the calculation. Missing evidence is labeled as missing rather than inferred.

Hover over a metric's information icon for a concise lineage summary. Select the same icon to open the full lineage view. The view reconciles every scenario-level metric using its persisted operands and displays:

- the formula, displayed value, independently recalculated value, and reconciliation result;
- each calculation operand;
- each material assumption's value, source, trust, validation, and approval state;
- linked evidence filenames and record counts;
- scenario, source-map, and validation-report identifiers.

A mismatch is disclosed for review rather than treated as verified. Missing operands or evidence remain visibly missing.

When an evidence filename is available, select it to open the retained original through BORB. BORB checks your deal-room viewing permission, verifies the stored file checksum, prevents shared caching, and records the access in the review trail. Files uploaded before governed original-file retention was introduced cannot be reconstructed; BORB reports those originals as unavailable.

## 🧮 Portfolio Policy Score

The Portfolio Policy Score is a reproducible compliance score, not a subjective quality grade. It is calculated from weighted scenario pass rates for DSCR, ROI, NOI, cap rate, cash-on-cash return, and debt yield.

Use the score information icon to see each metric's pass rate, normalized weight, and point contribution. If a metric is unavailable, BORB discloses that omission and normalizes the available weights. If no metrics can be scored, the result is **Unrated / N/A**, not zero.

## 📄 Generate IC Package

**Generate IC Package** replaces the former generic dashboard PDF export. BORB rebuilds the package from authenticated server records and opens an institutional print view that can be reviewed or saved as PDF.

The package includes:

- executive decision posture;
- decision readiness, owners, reviewers, and approval authority;
- exceptions and the decisions they prevent;
- KPI policy analysis and provenance;
- score decomposition;
- model versions and freshness dates.

The package reflects the state available when it is generated. Review unresolved exceptions and missing evidence before relying on it for an investment decision.

## 🎨 Status Colors

BORB uses a consistent status grammar:

- **Emerald:** cleared or ready to advance.
- **Amber:** human review or judgment required.
- **Rose:** a blocker prevents a conclusion or decision.
- **Cyan:** assumptions or calculations require refresh.
- **Violet:** governance, ownership, authority, or approval.
- **Blue:** explanatory information.
- **Slate:** neutral, unavailable, or unclassified.

## ✅ What Users Can Do

- Review decision readiness and explicit exceptions.
- Resume the highest-priority underwriting decision.
- Navigate to leads and scenarios.
- Open simulations, optimizations, comparisons, and reports.
- Generate an institutional decision package.
- Find support resources when workflow guidance is needed.

## 📝 What To Document Publicly

- Where primary navigation lives.
- Where common actions appear.
- How to interpret top-level summaries.
- Recommended first steps for new users.

## 🚀 Good First Steps

1. Start on Welcome and follow the single recommended action.
2. Open Decision Center to understand active exceptions and prevented decisions.
3. Resolve refresh, review, and promotion requirements in the appropriate queue.
4. Inspect KPI policy and provenance details before relying on material conclusions.
5. Generate the IC Package only after reviewing readiness, governance, and evidence gaps.

## 👤 Keep The Guide User-Facing

Avoid implementation details, internal routes, admin-only surfaces, and private troubleshooting steps.

## 🛠️ Maintenance Notes

- Update this README when dashboard navigation, major entry points, or first-run workflow guidance changes.
- Do not include internal routes, component names, or admin-only surfaces.
