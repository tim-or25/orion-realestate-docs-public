# BORB Architecture Diagrams

These diagrams capture the high-level redesign of BORB as a market-grounded, constraint-aware institutional underwriting system.

## 1. Product Flow Diagram

```mermaid
flowchart TD
    A["User Enters BORB"] --> B{"Choose Entry Mode"}

    B --> C["Path A: Start from Known Assumptions"]
    B --> D["Path B: Start from Target Metrics / Constraints"]

    C --> E["Deal / Asset Intake<br/>Manual Input<br/>Bulk Upload<br/>Existing Scenario"]
    D --> F["Target Setup<br/>IRR Target<br/>Cap Rate Target<br/>DSCR Floor<br/>Price Limits<br/>Stress Constraints"]

    E --> G["Shared Market Data Foundation"]
    F --> G

    G --> H["Market Benchmark Extraction<br/>Vendor-backed market rents<br/>Cap rates<br/>Vacancy<br/>Growth<br/>Financing context"]

    H --> I["Assumption Validation + Provenance<br/>Vendor-backed<br/>User-entered<br/>Inferred<br/>Out-of-bounds"]

    I --> J["Underwriting Problem Layer"]

    J --> K["Path A Resolution<br/>Validate<br/>Assist missing assumptions<br/>Complete assumption set"]
    J --> L["Path B Resolution<br/>Reverse solve<br/>Constraint solve<br/>Feasible region search"]

    K --> M["Scenario Generation"]
    L --> N["Feasible Scenario Set<br/>Market-Aligned<br/>Conservative<br/>Stretched"]
    N --> M

    M --> O["Scenario Store<br/>Canonical runnable scenario unit"]

    O --> P["Simulation Engine"]
    O --> Q["Optimization Engine"]
    O --> R["IRR / Return Lab"]
    O --> S["Valuation Engine"]
    O --> T["Compare Engine"]

    P --> U["Decision Layer"]
    Q --> U
    R --> U
    S --> U
    T --> U

    U --> V["Outputs<br/>Sensitivity<br/>Constraint breaches<br/>Target feasibility<br/>Thesis invalidation<br/>Scenario memory<br/>Snapshots / history"]
```

## 2. UML-ish Component Diagram

```mermaid
classDiagram
    class MarketDataFoundation {
      +fetchBenchmarks(assetType, geo, dealContext)
      +normalizeVendorData()
      +exposeMarketRanges()
    }

    class AssumptionValidationEngine {
      +validateAgainstMarket(assumptions, benchmarks)
      +flagOutOfBounds()
      +assignTrustLevel()
      +buildProvenanceMap()
    }

    class UnderwritingProblem {
      +entryMode
      +knownAssumptions
      +targetMetrics
      +constraints
      +marketContext
      +trustState
    }

    class ReverseSolveEngine {
      +solve(problem, benchmarks, constraints)
      +generateFeasibleSet()
      +rankByMarketAlignment()
    }

    class ScenarioGenerator {
      +fromKnownAssumptions(problem)
      +fromFeasibleSolutions(solutionSet)
      +buildScenario()
    }

    class ScenarioStore {
      +saveScenario()
      +loadScenario()
      +versionScenario()
    }

    class SimulationEngine {
      +runSensitivityAnalysis(scenario)
      +stressAssumptions(scenario)
    }

    class OptimizationEngine {
      +optimizeWithinMarketBounds(scenario)
      +explainOptimizedChanges()
    }

    class IRRLab {
      +runDeterministicIRR(scenario)
      +runMonteCarlo(scenario)
      +modelRefiAndExit(scenario)
    }

    class ValuationEngine {
      +deriveValuation(scenario, benchmarks)
    }

    class CompareEngine {
      +compareScenarios(scenarios)
      +rankScenarios()
      +highlightTrustDifferences()
    }

    class DecisionLayer {
      +summarizeDrivers()
      +identifyConstraintBreaches()
      +surfaceInvalidationRisks()
      +storeDecisionMemory()
    }

    MarketDataFoundation --> AssumptionValidationEngine
    AssumptionValidationEngine --> UnderwritingProblem
    UnderwritingProblem --> ReverseSolveEngine
    UnderwritingProblem --> ScenarioGenerator
    ReverseSolveEngine --> ScenarioGenerator
    ScenarioGenerator --> ScenarioStore

    ScenarioStore --> SimulationEngine
    ScenarioStore --> OptimizationEngine
    ScenarioStore --> IRRLab
    ScenarioStore --> ValuationEngine
    ScenarioStore --> CompareEngine

    SimulationEngine --> DecisionLayer
    OptimizationEngine --> DecisionLayer
    IRRLab --> DecisionLayer
    ValuationEngine --> DecisionLayer
    CompareEngine --> DecisionLayer
```

## 3. Reverse-Solve Decision Logic

```mermaid
flowchart LR
    A["Target Metrics / Constraints"] --> B["Market Bounds"]
    B --> C["Constraint Engine"]
    C --> D["Feasible Solution Search"]

    D --> E["Market-Aligned"]
    D --> F["Conservative"]
    D --> G["Stretched"]

    E --> H["Rank 1: Market alignment"]
    F --> I["Rank 2: Constraint satisfaction"]
    G --> J["Rank 3: Target fit"]
    J --> K["Rank 4: Robustness / sensitivity"]
```

## 4. Trust / Provenance Model

```mermaid
flowchart TD
    A["Any Assumption in BORB"] --> B{"Source Type"}

    B --> C["Vendor-backed"]
    B --> D["User-entered"]
    B --> E["Inferred"]
    B --> F["Out-of-bounds"]

    C --> G["High Trust"]
    D --> H["Medium Trust if market-valid"]
    E --> I["Medium / Low Trust"]
    F --> J["Low Trust + Warning"]

    G --> K["Used by all engines"]
    H --> K
    I --> K
    J --> K
```

## 5. Current-to-Future Module Mapping

```mermaid
flowchart TD
    A["Current BORB"] --> B["Onboarding"]
    A --> C["Simulation"]
    A --> D["Optimization"]
    A --> E["IRR"]
    A --> F["Valuation"]
    A --> G["Compare"]

    H["New Core Foundation"] --> I["Market Data Foundation"]
    H --> J["Assumption Validation + Provenance"]
    H --> K["Underwriting Problem Layer"]
    H --> L["Reverse Solve / Constraint Engine"]

    I --> B
    I --> C
    I --> D
    I --> E
    I --> F
    I --> G

    J --> B
    J --> C
    J --> D
    J --> E
    J --> F
    J --> G

    K --> B
    K --> L
    L --> E
    L --> C
    L --> D
    L --> G
```
