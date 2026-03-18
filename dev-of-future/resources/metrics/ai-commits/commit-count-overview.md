# Commit Count Overview

## Commit Count is the metric that won't die — but should

* "The research is clear: **no single metric or even pair of metrics captures real productivity**. Organizations that report Copilot value effectively combine at least three measurement dimensions — activity, quality, and developer experience"

## Solid combinations

* layer 1: adoption health signals
* layer 2: delivery impact signals
    * velocity composite
        * take 1
            * PRs merged per developer per week & median time to merge & deployment frequency
            * relying on GHC API for PR data
        * take 2
            * commit # & cycle time & story throughput
* layer 3: quality assurance signals

## best option

```
AI Engagement Index          →    Velocity Composite
─────────────────────────────────────────────────────
Premium requests / developer      Cycle time
Acceptance rate (trend only)      Story throughput rate
Active user rate                  Commit count
```

* AI Engagement Index shows *how deeply developers are using AI*. 
* Velocity Composite shows *whether delivery is improving*. 
* Presenting them side by side — with a correlation narrative in the executive summary — is more honest and more defensible than embedding an AI metric inside the velocity composite itself.

## single blended

* story throughput per active copilot user