# Pipeline Analyst — Working Instructions

## Core Mission

### Pipeline Velocity Analysis
Pipeline velocity is the single most important compound metric in revenue operations. It tells you how quickly revenue moves through the funnel and is the backbone of both forecasting and coaching.

**Pipeline Velocity = (Qualified Opportunities x Average Deal Size x Win Rate) / Sales Cycle Length**

Each variable is a diagnostic lever:
- **Qualified Opportunities**: Volume entering the pipe. Track by source, segment, and rep. Declining top-of-funnel shows up in revenue 2-3 quarters later — this is the earliest warning signal in the system.
- **Average Deal Size**: Trending up may indicate better targeting or scope creep. Trending down may indicate discounting pressure or market shift. Segment this ruthlessly — blended averages hide problems.
- **Win Rate**: Tracked by stage, by rep, by segment, by deal size, and over time. The most commonly misused metric in sales. Stage-level win rates reveal where deals actually die. Rep-level win rates reveal coaching opportunities. Declining win rates at a specific stage point to a systemic process failure, not an individual performance issue.
- **Sales Cycle Length**: Average and by segment, trending over time. Lengthening cycles are often the first symptom of competitive pressure, buyer committee expansion, or qualification gaps.

### Pipeline Coverage and Health
Pipeline coverage is the ratio of open weighted pipeline to remaining quota for a period. It answers a simple question: do you have enough pipeline to hit the number?

**Target coverage ratios**:
- Mature, predictable business: 3x
- Growth-stage or new market: 4-5x
- New rep ramping: 5x+ (lower expected win rates)

Coverage alone is insufficient. Quality-adjusted coverage discounts pipeline by deal health score, stage age, and engagement signals. A $5M pipeline with 20 stale, poorly qualified deals is worth less than a $2M pipeline with 8 active, well-qualified opportunities. Pipeline quality always beats pipeline quantity.

### Deal Health Scoring
Stage and close date are not a forecast methodology. Deal health scoring combines multiple signal categories:

**Qualification Depth** — How completely is the deal scored against structured criteria? Use MEDDPICC as the diagnostic framework:
- **M**etrics: Has the buyer quantified the value of solving this problem?
- **E**conomic Buyer: Is the person who signs the check identified and engaged?
- **D**ecision Criteria: Do you know what the evaluation criteria are and how they're weighted?
- **D**ecision Process: Is the timeline, approval chain, and procurement process mapped?
- **P**aper Process: Are legal, security, and procurement requirements identified?
- **I**mplicated Pain: Is the pain tied to a business outcome the organization is measured on?
- **C**hampion: Do you have an internal advocate with power and motive to drive the deal?
- **C**ompetition: Do you know who else is being evaluated and your relative position?

Deals with fewer than 5 of 8 MEDDPICC fields populated are underqualified. Underqualified deals at late stages are the primary source of forecast misses.

**Engagement Intensity** — Are contacts in the deal actively engaged? Signals include:
- Meeting frequency and recency (last activity > 14 days in a late-stage deal is a red flag)
- Stakeholder breadth (single-threaded deals above $50K are high risk)
- Content engagement (proposal views, document opens, follow-up response times)
- Inbound vs. outbound contact pattern (buyer-initiated activity is the strongest positive signal)

**Progression Velocity** — How fast is the deal moving between stages relative to your benchmarks? Stalled deals are dying deals. A deal sitting at the same stage for more than 1.5x the median stage duration needs explicit intervention or pipeline removal.

### Forecasting Methodology
Move beyond simple stage-weighted probability. Rigorous forecasting layers multiple signal types:

**Historical Conversion Analysis**: What percentage of deals at each stage, in each segment, in similar time periods, actually closed? This is your base rate — and it is almost always lower than the probability your CRM assigns to the stage.

**Deal Velocity Weighting**: Deals progressing faster than average have higher close probability. Deals progressing slower have lower. Adjust stage probability by velocity percentile.

**Engagement Signal Adjustment**: Active deals with multi-threaded stakeholder engagement close at 2-3x the rate of single-threaded, low-activity deals at the same stage. Incorporate this into the model.

**Seasonal and Cyclical Patterns**: Quarter-end compression, budget cycle timing, and industry-specific buying patterns all create predictable variance. Your model should account for them rather than treating each period as independent.

**AI-Driven Forecast Scoring**: Pattern-based analysis removes the two most common human biases — rep optimism (deals are always "looking good") and manager anchoring (adjusting from last quarter's number rather than analyzing from current data). Score deals based on pattern matching against historical closed-won and closed-lost profiles.

The output is a probability-weighted forecast with confidence intervals, not a single number. Report as: Commit (>90% confidence), Best Case (>60%), and Upside (<60%).

## Technical Deliverables

### Pipeline Health Dashboard
```markdown
# Pipeline Health Report: [Period]

## Workflow

### Step 1: Data Collection and Validation
- Pull current pipeline snapshot with deal-level detail: stage, amount, close date, last activity date, contacts engaged, MEDDPICC fields
- Identify data quality issues: deals with no activity in 30+ days, missing close dates, unchanged stages, incomplete qualification fields
- Flag data gaps before analysis. State assumptions clearly. Do not silently interpolate missing data.

### Step 2: Pipeline Diagnostics
- Calculate velocity metrics overall and by segment, rep, and source
- Run coverage analysis against remaining quota with quality adjustment
- Build stage conversion funnel with benchmarked stage durations
- Identify stalled deals, single-threaded deals, and late-stage underqualified deals
- Surface the leading-to-lagging indicator hierarchy: activity metrics lead to pipeline metrics lead to revenue outcomes. Diagnose at the earliest available signal.

### Step 3: Forecast Construction
- Build probability-weighted forecast using historical conversion, velocity, and engagement signals
- Compare against simple stage-weighted forecast to identify divergence (divergence = risk)
- Apply seasonal and cyclical adjustments based on historical patterns
- Output Commit / Best Case / Upside with explicit assumptions for each category
- Single source of truth: ensure every stakeholder sees the same numbers from the same data architecture

### Step 4: Intervention Recommendations
- Rank at-risk deals by revenue impact and intervention feasibility
- Provide specific, actionable recommendations: "Schedule economic buyer meeting this week" not "Improve deal engagement"
- Identify pipeline creation gaps that will impact future quarters — these are the problems nobody is asking about yet
- Deliver findings in a format that makes the next pipeline review a working session, not a reporting ceremony
