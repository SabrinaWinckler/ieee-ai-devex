# IEEE AI-Powered Developer Experience (DevEx) Study

## Project Overview

This repository contains the complete dataset and methodology documentation for a mixed-methods research study investigating how AI coding assistants (specifically GitHub Copilot and Windsurf) impact Developer Experience across three core dimensions of the DevEx framework [Noda et al., 2023](https://queue.acm.org/detail.cfm?id=3595878).

### Repository Structure

The datasets in this repository directly support the following analysis components:

1. **Quantitative Analysis** - Telemetry data from GitHub Copilot users
2. **Qualitative Analysis** - Participant observation quote transcripts
3. **Mixed-Methods Integration** - Cross-validation of quantitative metrics with qualitative insights

---

## Study Participants & Data Collection Funnel

### Participant Distribution

```
┌─────────────────────────────────────────────────────────┐
│  TOTAL TECHNICAL CONTRIBUTORS (T=0)                     │
│  36 people                                               │
│  (100%)                                                  │
└────────────────┬────────────────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────────────────┐
│  MEETING PARTICIPANTS                                    │
│  26 people                                               │
│  (72.2% of total)                                        │
│  Participated in experience sharing session              │
└────────────────┬────────────────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────────────────┐
│  QUALITATIVE RESPONDENTS                                 │
│  9 people                                                │
│  (25% of total / 34.6% of meeting participants)          │
│  Reported detailed experiences with AI tools             │
└────────────────┬────────────────────────────────────────┘
                 │
                 ├─────────────────│────────────────────────┐
                 │                 │                        │
                 ▼                 │                        ▼
        ┌─────────────────────┐    │          ┌──────────────────────┐
        │  COPILOT USERS      │    │          │  WINDSURF USERS      │
        │  21 people          │    │          │  2 people            │
        │  (58.3% of total)   │    │          │  (5.6% of total)     │
        │  WITH TELEMETRY     │    │          │  QUALITATIVE ONLY    │
        └─────────────────────┘    │          └──────────────────────┘
                                   |
                                   │
                                   ▼
                      ┌──────────────────────┐
                      │  INACTIVE USERS      │
                      │  (7-30+ days)        │
                      │  4 people            │
                      │  (11.1% of total)    │
                      │                      │
                      │  + 1 person          │
                      │  (>30 days inactive) │
                      │  (2.8% of total)     │
                      └──────────────────────┘

NO AI-TOOL SUBSCRIPTION: 8 people (22.2%)
```

### Key Metrics

| Category | Count | Percentage | Details |
|----------|-------|-----------|---------|
| **Total Technical Contributors** | 36 | 100% | Organization tech team at study period |
| **Meeting Participants** | 26 | 72.2% | Attended experience sharing session |
| **Qualitative Respondents** | 9 | 25.0% | Provided detailed narrative data |
| **GitHub Copilot Users** | 21 | 58.3% | With telemetry data available |
| **Windsurf Users** | 2 | 5.6% | Qualitative data only |
| **No AI Tool Subscription** | 8 | 22.2% | Non-adopters |
| **Copilot Inactive (7-30 days)** | 4 | 11.1% | Moderate inactivity |
| **Copilot Inactive (>30 days)** | 1 | 2.8% | Extended inactivity |

---

## Data Collection Methodology

### Phase 1: Quantitative Data Collection
- **Source**: Internal survey + GitHub Copilot telemetry data
- **Sample**: 36 technical unit person (Github Copilot = 26, Windsurf = 2, No tool Subscription = 8)
- **Type**: Tool adoption mapping, usage frequency, preferred AI coding assistants
- **Purpose**: Establish a baseline landscape of current AI tool usage across the team — identifying how many developers use GitHub Copilot, Windsurf, other assistants, or no AI tooling at all

### Phase 2: Qualitative Data Collection
- **Method**: Participant observation
- **Sample**: 9 reporterd in-depth reflections out of 26 meeting participants (from a 36-person technical unit)
- **Type**: Experience narratives, challenges, benefits, recommendations
- **Purpose**: Understand subjective developer experience and contextual factors

### Phase 3: Mixed-Methods Integration
- **Integration Point**: Cross-validation of quantitative usage patterns with qualitative experience narratives
- **Analysis**: Correlation between tool usage frequency and reported satisfaction levels
- **Outcome**: Comprehensive understanding of AI tool impact on DevEx

---

## DevEx Framework Dimensions

This study analyzes AI coding assistant impact across three core DevEx dimensions:

1. **Dimension 1: Flow State [Productivity & Efficiency]**
   - Telemetry: Code completion acceptance rates, session frequency
   - Qualitative: User-reported time savings and workflow integration

2. **Dimension 2: Feedback Loops [Developer Satisfaction & Engagement]**
   - Telemetry: Usage consistency and adoption patterns
   - Qualitative: Experience narratives, perceived value, adoption barriers

3. **Dimension 3: Cognitive Load [Learning & Skill Development]**
   - Telemetry: Tool engagement patterns across experience levels
   - Qualitative: Perceptions of learning outcomes and skill enhancement

---

## Dataset Files & Mapping to Analysis

### Quantitative Datasets

- **`copilot_telemetry_data_from_july_to_august.csv`** → Used in *"The Fintech Case Study"* (Quantitative data subsection), *"Adoption and Usage"* (usage trends and acceptance rate analysis), and **Figure 1** (daily suggestions vs. acceptances, May–Aug 2025)

**How figure 1 is generated?**
Bellow figure was gattered from Copilot Metrics Viewer Tool [v2.0.2](https://github.com/github-copilot-resources/copilotmetrics-viewer/tree/v2.0.2)
<img width="924" height="530" alt="aceptanceRateByCount (1)" src="https://github.com/user-attachments/assets/1c3254b7-4507-40ad-964a-c62707899d01" />

The telemetry data used in this analysis is publicly available in the study repository as a CSV file. Each row in the file represents an aggregated daily snapshot of GitHub Copilot usage across the active users, containing the following relevant columns: `date`, `suggestions_count`, `acceptances_count`, `lines_suggested`, and `lines_accepted`.

To reproduce the usage trend visualized in Figure 1, one can group the data by `date` and plot `suggestions_count` against `acceptances_count` over time, making fluctuations in daily engagement immediately apparent. The suggestion-level acceptance rate — reported as 24.23% across the full study period — is computed as:

$$\text{Acceptance Rate} = \frac{\sum \text{Acceptances Count}}{\sum \text{Suggestions Count}} \times 100$$

Similarly, the line-level acceptance rate of 16.36% is derived from:

$$\text{Line Acceptance Rate} = \frac{\sum \text{Lines Accepted}}{\sum \text{Lines Suggested}} \times 100$$

| Reported Metric | CSV Column |
|---|---|
| 47,336 prompts | `suggestions_count` |
| 98,797 suggestions | `lines_suggested` |
| 24.23% acceptance rate | `acceptances_count / suggestions_count` |
| 16.36% line acceptance | `lines_accepted / lines_suggested` |

Together, these four fields are sufficient to replicate the aggregate metrics reported in this study (47,336 prompts, 98,797 suggestions, and a 24.23% suggestion-level acceptance rate among 21 developers over ten months).

---

> **⚠️ Note on Data Availability and Retention**
>
> The CSV file available in the repository covers only the period from **July to August 2025**, while the article presents data from **May to August 2025**. As a result, the values in the replication package will be lower than the cumulative figures reported in the paper — this is expected and does not indicate inconsistency.
>
> This limitation stems from a platform retention issue: **GitHub Copilot Metrics Viewer (v2.0.2)** had limited historical data retention. Figure 1 was exported during the study period. After upgrading to **v2.1.2**, access to raw telemetry for **May–June 2025** was no longer available, leaving only the July–August 2025 data for the replication package. Although this reduces data granularity, the cumulative metrics and visual trends still align with the reported statistics, preserving trend validity.
>
> For GitHub Copilot metrics, the analytic population consisted of the **21 active users** during the observation window. As noted, **Windsurf**'s individual subscription model does not provide organizational telemetry, so its usage was analyzed qualitatively only.

**copilot_telemetry_data_from_july_to_august.csv`**: This file contains quantitative usage metrics from GitHub Copilot collected between July and August 2025.

### Columns:

| Column | Description |
|--------|-------------|
| **Date** | Date of the recorded metrics (YYYY-MM-DD format) |
| **Total Active Users** | Number of users with active Copilot licenses |
| **Total Engaged Users** | Number of users who actively used Copilot features |
| **Feature Type** | Type of Copilot feature used (IDE Code Completions, IDE Chat, Dotcom Chat) |
| **Editor Name** | IDE/Editor used (vscode, JetBrains, Vim) |
| **Model Name** | AI model used (default) |
| **Is Custom Model** | Whether a custom-trained model was used (true/false) |
| **Custom Model Training Date** | Training date for custom models (if applicable) |
| **Language Name** | Programming language used (csharp, python, java, typescript, etc.) |
| **Feature Engaged Users** | Number of users engaged with the specific feature |
| **Suggestions Count** | Total number of code suggestions generated |
| **Acceptances Count** | Number of suggestions accepted by users |
| **Lines Suggested** | Total lines of code suggested |
| **Lines Accepted** | Total lines of code accepted |
| **Chats** | Number of chat interactions (for IDE Chat feature) |
| **Chat Insertion Events** | Number of times chat suggestions were inserted into code |
| **Chat Copy Events** | Number of times chat responses were copied |
| **PR Summaries Created** | Number of pull request summaries generated |
| **Repository Name** | Repository where the activity occurred |

### Key Metrics for Analysis:

- **Acceptance Rate**: `Acceptances Count / Suggestions Count` - measures how useful suggestions are
- **Lines Acceptance Rate**: `Lines Accepted / Lines Suggested` - measures code quality acceptance
- **Engagement Rate**: `Total Engaged Users / Total Active Users` - measures tool adoption

---


### Qualitative Datasets

- **Coding Table: `devex_rationale_quotes.csv`** → Used in *"The Fintech Case Study"* (Qualitative data subsection), *"Practitioner's Perspectives on GitHub Copilot and Windsurf"* (**Figure 2** and **Table 2**), and *"Key Findings"* (productivity–validation tension)

### Analysis & Results Files

**devex_rationale_quotes.csv**: This file contains the qualitative analysis data from participant observation in a meeting with 26 practitioners, of whom 9 submitted in-depth reflections (n = 9) on their experiences with AI-assisted tools.

### Columns:

| Column | Description |
|--------|-------------|
| **DevEx_Dimension** | The Developer Experience dimension associated with the quote (Flow State, Feedback Loops, or Cognitive Load) |
| **Quote** | Direct quote from the participant during the meeting |
| **Participant** | Participant identifier (P1-P9) |
| **Role** | Professional role of the participant (Tech Lead, Mid-level Dev, CTO, Specialist) |
| **Tool** | AI tool used by the participant: **W** = Windsurf, **C** = GitHub Copilot |
| **Impact** | Perceived impact on DevEx: **Positive** (↑), **Negative** (↓), or **Neutral** (±) |
| **Rationale** | Explanation of why the quote was linked to the specific DevEx dimension |

### DevEx Dimensions:

- **Flow State**: Quotes related to immersive coding experiences, productivity, and uninterrupted work
- **Feedback Loops**: Quotes about receiving guidance, assistance, and iterative feedback during development
- **Cognitive Load**: Quotes concerning mental effort, learning, task complexity, and review burden


---

## How Datasets Support Key Findings

This section explicitly maps each dataset to the specific findings, paper sections, and figures they support.

### `copilot_telemetry_data_from_july_to_august.csv` → Quantitative Findings

| Dataset columns | Supports | Where in the paper |
|---|---|---|
| `suggestions_count`, `acceptances_count` | 24.23% suggestion-level acceptance rate; comparison with Ziegler et al.'s 27% benchmark | Section *"Adoption and Usage"*, paragraph 3 |
| `lines_suggested`, `lines_accepted` | 16.36% line-level acceptance rate; evidence of stable integration over 10 months | Section *"Adoption and Usage"*, paragraph 3 |
| `date` + `suggestions_count` + `acceptances_count` (grouped by day) | Daily volatility of suggestions vs. acceptances; dips interpreted as task-dependent usage | **Figure 1** |
| All columns aggregated | Cumulative totals: 47,336 prompts, 98,797 suggestions — evidence of sustained tool engagement | Abstract; Section *"Adoption and Usage"* |
| `suggestions_count` by date | Heterogeneous usage trends: 4 users inactive >7 days, 1 user inactive >30 days | Section *"Adoption and Usage"*, paragraph 1 |

**Key finding directly supported:** AI-assisted tools show stable, sustained integration in a fintech setting, with an acceptance rate consistent with prior literature — supporting the argument that GitHub Copilot's value extends beyond direct acceptance to inspiration and partial adaptation.

---

### `devex_rationale_quotes.csv` → Qualitative Findings

| Dataset columns | Supports | Where in the paper |
|---|---|---|
| `DevEx_Dimension` + `Impact` | Frequency counts of themes per DevEx dimension (e.g., Cognitive Load most frequent at 33%) | **Table 2** — *Frequency of Qualitative Themes by DevEx Dimension* |
| `Quote` + `Participant` + `Role` + `Tool` | Illustrative practitioner excerpts, annotated by tool (C/W) and impact (↑ ↓ ±) | **Figure 2** — *Practitioners' perspectives grouped by DevEx recurring themes* |
| `Rationale` | Audit trail for deductive thematic coding aligned with the three DevEx dimensions | Section *"The Fintech Case Study"* — Qualitative data subsection |
| `DevEx_Dimension = "Cognitive Load"` rows | Productivity–validation tension: developers report review and guidance burden alongside productivity gains | Section *"Key Findings"*, paragraph 1–2 |
| `DevEx_Dimension = "Flow State"` rows | 5 participants report flow state improvements (transformative impact, learning acceleration, problem-solving) | Section *"Practitioner's Perspectives"*, paragraph 3 |
| `DevEx_Dimension = "Feedback Loops"` rows | 2 participants liken AI to senior developers or effective assistants, signaling a shift in how developers conceptualize the programming process | Section *"Practitioner's Perspectives"*, paragraph 4 |

**Key finding directly supported:** The productivity–validation paradox — AI tools enhance Flow State while simultaneously increasing Cognitive Load through validation requirements — is evidenced by the distribution of coded quotes across DevEx dimensions, particularly the negative-impact Cognitive Load entries (*"Review agent's work"*, *"Guide the agent"*, *"Steer the LLM Agent"*) coexisting with positive Flow State entries (*"It was a game changer"*, *"Accelerated learning curve"*).

---

## Study Limitations & Data Considerations

1. **Selection Bias**: Participants self-selected; may represent more positive adopters
2. **Sample Size**: Qualitative sample (n=9) limits generalizability of narrative findings
3. **Windsurf Representation**: Limited adoption (n=2) prevents robust comparative analysis
4. **Temporal Scope**: Data captured at single time point; longitudinal trends not available
5. **Telemetry Gaps**: 2 Windsurf users have qualitative data only; comparative telemetry limited

---

## Reproducibility & Transparency

All data has been anonymized to protect participant privacy while maintaining analytical integrity:

- Pratictioner identifiers replaced with randomized codes (P01-Pn)
- Date information generalized to study week/month
- Identifying demographic details removed from narratives
- Organization name redacted from all files

For questions about data access or methodology, please contact the research team or open an issue in this repository.

---






