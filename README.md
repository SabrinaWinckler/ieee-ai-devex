# Qualitative Analysis - Data Files Description

This document describes the data files used in the qualitative and quantitative analysis of Developer Experience (DevEx) with AI coding assistants.

---

## 1. quali_devex_rationale_quotes.csv

This file contains the qualitative analysis data from participant observation in a meeting with 26 practitioners and 9 reporters (n=9) that share your experience.

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

## 2. july_to_august.csv

This file contains quantitative usage metrics from GitHub Copilot collected between July and August 2025.

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

## Usage in Research

These datasets support the mixed-methods analysis of how AI coding assistants impact Developer Experience across three core dimensions defined by the DevEx framework (Noda et al., 2023).
