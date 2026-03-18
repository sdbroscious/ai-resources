# Measuring GitHub Copilot adoption for CIO-level reporting

**The most defensible approach to measuring team-level Copilot adoption combines three metric tiers — breadth of usage, depth of engagement, and downstream impact — rather than relying on any single number.** GitHub’s native metrics (GA as of February 2026) now expose  user-level interaction counts, acceptance rates, lines-of-code data, and PR lifecycle signals through both a dashboard and API, but team-level aggregation requires manual assembly from user-level data. Enterprise benchmarks converge on a **~30% suggestion acceptance rate** as the industry norm,   **60–80% active usage** among licensed developers as a realistic adoption target,  and **2–3 hours per week** in developer-reported time savings. The sections below lay out exactly what GitHub exposes, how to construct a continuous adoption score with defensible thresholds, and what leading enterprises actually report.

-----

## GitHub now offers two metric systems — and neither natively aggregates by team

GitHub maintains two distinct Copilot metrics systems as of March 2026, plus a separate billing API for premium requests. Understanding the architecture is essential before building any reporting layer.

**The new Copilot Usage Metrics API** (GA February 27, 2026) returns download links to NDJSON files containing per-user, per-day records. Each record includes `user_initiated_interaction_count` (explicit prompts sent), `code_generation_activity_count` (distinct code output events), `code_acceptance_activity_count` (suggestions applied to files),  boolean flags for CLI/agent/chat usage, lines-of-code fields (`loc_added_sum`, `loc_suggested_to_add_sum`, `loc_deleted_sum`),  and chat-mode breakdowns across agent, ask, edit, and custom modes.  Enterprise and organization-level aggregate endpoints also exist, along with **PR lifecycle metrics** including `pull_requests.total_created`, `median_minutes_to_merge`, and `total_created_by_copilot`.   Data is available from October 10, 2025 onward,  with a two-day processing lag. 

The critical gap: **the new API has no team-level endpoint**. It supports enterprise, organization, and user-level scopes only  — no GitHub Teams grouping, no repository-level filtering. Organizations wanting team-level views must download user-level NDJSON files and aggregate them against their own team rosters. The **legacy Copilot Metrics API** (`/orgs/{org}/team/{team_slug}/copilot/metrics`) does support GitHub Teams natively,  returning daily aggregates including `total_active_users`, `total_engaged_users`, suggestion counts, acceptance counts, and lines-of-code by language and editor. However, this endpoint **shuts down April 2, 2026**,  and requires a minimum of five licensed members per team to return data.  

Premium request consumption — increasingly important as Copilot shifts toward model-choice pricing — is tracked through GitHub’s **Billing Usage API**, entirely separate from the metrics system. Enterprise owners can see per-user premium request data; organization owners cannot.  This split means a complete CIO dashboard requires pulling from at least two API systems.

The admin dashboard (available at both enterprise and org levels) surfaces the same data visually,  including a **Code Generation Dashboard** (launched December 2025) showing  lines of code changed with AI, agent contribution percentages, and model-by-language breakdowns.  Dashboard data can be exported as NDJSON for custom analysis.  

-----

## How to construct a continuous adoption score with classification thresholds

A binary “using/not using” metric tells executives almost nothing. The practical solution is a **weighted composite index** that captures breadth, depth, and trust, then applying tier thresholds to classify teams for portfolio-level reporting.

### The composite formula

The most defensible approach, synthesized from the DX AI Measurement Framework,  Microsoft’s AI Adoption Score methodology, and practitioner implementations, is:

**Team AI Adoption Score = (0.50 × Breadth) + (0.30 × Depth) + (0.20 × Sentiment)**

Where each component is normalized to a 0–100 scale:

- **Breadth** = (Weekly Active Users / Team Size) × 100. This is the single most important early signal — it answers “what fraction of the team is actually using the tool?” GitHub’s API provides the `user_initiated_interaction_count` field per user per day,   which can be aggregated to compute WAU per team.
- **Depth** = min(Team Acceptance Rate / 0.30, 1.0) × 100. This normalizes against the **30% enterprise benchmark**,  so a team matching the industry average scores 100 on depth. Acceptance rate is computed from `code_acceptance_activity_count / code_generation_activity_count` at the user level.  Teams below 15% are finding suggestions irrelevant or are only superficially engaged.
- **Sentiment** = Normalized developer satisfaction score from quarterly surveys (0–100). This counterbalances quantitative metrics that can be gamed and captures the qualitative signal that METR research has shown diverges from objective performance — experienced developers in one study believed AI made them **20% faster** while actually taking **19% longer**. 

### Classification thresholds for team-level reporting

Based on converging evidence from DX research, Faros AI benchmarks, Software.com’s engagement tiers, and enterprise case studies:

- **AI-Native** (Score ≥ 75): ≥80% WAU, ≥25% acceptance rate, multi-feature usage (completions + chat + agent). These teams have integrated AI into daily workflow. Shopify’s engineering org operated at this level after sustained rollout. 
- **AI-Adopting** (Score 50–74): 50–79% WAU, ≥20% acceptance rate, at least two Copilot features in use. Making real progress; focus enablement on remaining holdouts.
- **AI-Exploring** (Score 25–49): 20–49% WAU or acceptance rate below 20%. Early-stage adoption; likely facing toolchain friction, policy confusion, or skill gaps.
- **Non-Adopting** (Score < 25): Below 20% WAU. Requires direct investigation into blockers — regulatory constraints, tech stack incompatibility, or cultural resistance.

Microsoft’s internal research on M365 Copilot offers an additional calibration point: they found **≥3 days per week** (12 of 28 days) is the threshold at which users become habitual, long-term adopters.  Applying this to GitHub Copilot, a “meaningfully active” developer is one using the tool on at least 12 days per rolling 28-day window — a more defensible definition than GitHub’s default “any interaction counts.”

-----

## Defining “active user” requires more nuance than GitHub provides out of the box

GitHub’s default definition is generous: any user who receives a suggestion or sends a chat message counts as “active” for that day. This makes DAU/WAU/MAU figures look healthy but obscures the difference between a developer who accepted 50 suggestions and one who dismissed a single auto-triggered completion.

Practitioners have converged on a **tiered engagement model** that distinguishes three levels. **Active users** have Copilot installed and received suggestions (the tool fired). **Engaged users** accepted at least one suggestion, indicating conscious integration into workflow. **Power users** use Copilot across multiple features — completions, chat, and agent mode — on three or more days per week. The new API supports this segmentation: the `code_acceptance_activity_count` field distinguishes accepted from merely shown, while `used_agent`, `used_chat`, and `used_cli` booleans reveal feature breadth. 

For CIO reporting, the **engaged user rate** (users who accepted at least one suggestion / total licensed users) is more informative than raw active user count. Accenture’s field study found that **96% of developers who installed Copilot accepted a suggestion on Day 1**,   but sustained engagement plateaued at roughly **60%** of the treatment group after 18 months.  DX research confirms this ceiling: even at leading organizations, only about **60% of licensed developers** maintain active usage.   Setting expectations at this level prevents the “why aren’t we at 100%?” executive question.

The most common pitfall is conflating **license assignment with adoption**. One analysis of Microsoft 365 Copilot found that while 70% of Fortune 500 companies had purchased licenses, actual penetration across paid seats hovered at roughly 3%.  GitHub Copilot data from Faros AI shows that organizations actively re-engaging dormant users can increase adoption by **30%**  — suggesting that measurement and follow-up, not just procurement, drive outcomes.

-----

## Enterprise benchmarks show consistent patterns across large deployments

The most robust enterprise data comes from randomized controlled trials and large-scale observational studies, not vendor marketing. Here is what the evidence shows across organizations with 100+ developers:

**Accenture** ran a rigorous study with ~450 developers. Installation hit **81.4%** on Day 1;  the acceptance rate settled at **~30%**; developers retained **88%** of accepted code (meaning they didn’t immediately delete it).  PR throughput increased **8.7%**,  merge rates improved **15%**, and successful builds rose **84%**.  Notably, **67%** of developers used Copilot at least five days per week. 

**Microsoft’s internal RCT** across 1,663 developers revealed a sobering adoption curve:  only **8.5%** signed up in the first two weeks without prompting,  rising to 35% after reminder emails and eventually 75.6% in the treatment group.  Combined analysis across three experiments (Microsoft, Accenture, and an anonymous Fortune 100 company totaling 4,867 developers) showed a **26%** increase in weekly PR output.  

**Shopify** (~4,000 engineers) reached **80% adoption** relatively quickly,  with a **26% acceptance rate**.  VP Engineering Farhan Thawar noted the approach prioritized developer happiness over quantitative metrics  and found a positive correlation between AI tool usage and performance reviews.  **Mercedes-Benz** deployed across **5,000+ developers** and 115,000 repositories, reporting over 2 million accepted lines of code  and approximately 30 minutes of daily productivity savings per developer. 

**ZoomInfo** (400+ developers) published one of the few peer-reviewed studies, finding a **33% suggestion acceptance rate**, **72% developer satisfaction**, and roughly 20% self-reported time savings, with acceptance rates consistent across TypeScript, Java, Python, and JavaScript. 

McKinsey’s analysis of companies working with Jellyfish found that organizations with **80–100% developer AI adoption** saw productivity gains exceeding **110%**, while those above 60% adoption saw at least 25% improvement  — a nonlinear relationship that argues for pushing past the 60% plateau.

### The counterpoint data matters for credible reporting

**DORA’s 2024 survey** of 39,000 professionals found that a 25% increase in AI adoption correlated with a **1.5% decrease** in delivery throughput and **7.2% decrease** in delivery stability.  GitClear’s analysis of 153 million changed lines showed code churn **doubled** in 2024 versus pre-AI 2021, with AI-generated code exhibiting **41% higher churn**.  BlueOptima’s study of 218,000 developers found only **~4% productivity gains**, with 88% of developers reworking AI code before committing.  Gartner’s survey found **42% of engineering staff** report only 1–10% gains from AI, with 12% reporting zero gains.  These findings don’t invalidate Copilot’s value but are essential context for honest executive reporting — omitting them undermines credibility.

-----

## Building a defensible CIO dashboard requires four metric tiers

The most effective executive reporting framework — drawing from DX’s AI Measurement Framework (used by Booking.com, Intercom, and Block),  Gartner’s AI value metrics, and GitHub’s native data — organizes metrics into four tiers that answer progressively harder questions.

**Tier 1: Adoption reach** answers “are we using it?” Track license utilization rate (active seats / assigned seats over 28 days), WAU trend by team, feature adoption mix (what percentage of users have moved beyond basic completions to chat and agent mode),  and the team classification distribution described above. This tier is fully addressable from GitHub’s API data.

**Tier 2: Engagement quality** answers “how deeply are they using it?” Track acceptance rate trends (benchmark: **25–35%** is healthy),  AI code contribution rate (`loc_added_sum` from Copilot / total org lines added, framed explicitly as a floor estimate),  and suggestions accepted per developer per week as an intensity measure. The acceptance rate is the single metric most correlated with perceived productivity, according to GitHub’s own CACM-published research.  

**Tier 3: Productivity impact** answers “is it working?” Track PR throughput delta versus pre-adoption baseline (benchmark: **8–26% increase**),   cycle time changes (median time-to-merge is available directly from the API),   developer-reported time savings from quarterly surveys (benchmark: **2–3 hours/week**), and developer satisfaction scores. This tier requires combining API data with survey instruments.

**Tier 4: Business value** answers “is it worth the investment?” Calculate cost per active user (license cost / active users — not assigned users), net time savings (gross savings minus estimated rework, since research suggests roughly **37% of AI time savings** are offset by rework),  and quality counterbalances like change failure rate and code churn in AI-heavy repositories.

Two guardrails are non-negotiable for credible reporting. First, **never present LOC metrics as productivity proof** — they are adoption telemetry showing the tool is firing, not evidence of business value.   GitHub’s own documentation and internal practitioner guidance emphasize this distinction. Second, **always pair speed metrics with quality metrics**. Showing increased PR throughput without tracking change failure rate or code churn creates a one-sided narrative that erodes trust when problems surface.

-----

## Conclusion

The practical path to CIO-ready Copilot reporting has three steps. First, build an automated pipeline pulling user-level data from the new Copilot Usage Metrics API and aggregating it against your organizational team rosters — this manual assembly is necessary because GitHub’s new API eliminated the legacy team-level endpoint.  Second, implement the weighted composite score (50% breadth, 30% depth, 20% sentiment) with the four-tier classification to give executives a portfolio view of where adoption stands across the organization. Third, resist the temptation to report only favorable metrics: the **30% acceptance rate benchmark**,   the **60% active usage ceiling** at even leading organizations,  and the real counterpoint data from DORA and GitClear are what make the dashboard credible.

The most important insight from the enterprise evidence is that **measurement drives adoption, not just the reverse**. Microsoft found that simple enablement emails increased adoption by 26.4% within two weeks.  Faros AI found that re-engaging dormant users lifted adoption by 30%.  The CIO dashboard is not just a reporting artifact — it is an intervention tool, and the organizations treating it as such are the ones reaching the 80%+ adoption levels where nonlinear productivity gains begin to appear.