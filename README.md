# HealthTrust Watch

## Exploratory NLP Analysis of User-Reported Concerns in MyChart Healthcare App Reviews

HealthTrust Watch is an INFO 4360 course project that investigates how Natural Language Processing (NLP) can be used to understand user-reported concerns in digital health application reviews.

Following feedback from Phase I, the project has been refined to focus on **MyChart**, a single healthcare application, rather than comparing multiple applications. The analysis also expands beyond privacy to examine technical reliability, medical-record access, usability, customer support, data accuracy, and privacy or data control.

The project follows **Path B: Understanding and Extraction**, emphasizing descriptive analysis, issue identification, and interpretable findings rather than predictive modeling.

## 1. Problem Statement

Healthcare applications such as MyChart provide patients with digital access to medical information and services. However, users may experience difficulties involving application crashes, account access, navigation, customer support, and concerns about personal health information.

These experiences are often documented in unstructured app reviews, making it challenging for product teams to systematically identify recurring issues and understand their relative importance.

This project uses NLP techniques to analyze historical MyChart reviews, identify commonly discussed concerns, and explore how review patterns differ across ratings, time periods, and application versions.

The goal is to provide evidence-based insights that help stakeholders prioritize further investigation and potential product improvements.

## 2. Stakeholders

The primary stakeholders are digital health product managers and customer-experience teams responsible for improving application reliability, usability, accessibility, and user satisfaction.

Additional stakeholders include customer support and privacy teams, who may use the findings to investigate recurring service or data-control concerns.

## 3. Dataset

The project uses the **Health App Reviews for Privacy & Trust (HARPT)** dataset.

The original dataset contains approximately 480,450 reviews from 67 digital health applications covering 2011–2025.

For the revised project, the analysis will focus on reviews associated with **MyChart**.

Relevant dataset fields include:

- `content` — Original user review text
- `score` — Star rating
- `at` — Review date
- `app_name` — Application name
- `reviewCreatedVersion` — Application version, where available
- `trust_dimension` — Existing dataset annotation, used only as unverified reference metadata

The project will evaluate missing values, duplicate records, review-text quality, date coverage, rating distributions, and app-version completeness before conducting detailed analysis.

Existing trust-related annotations will not be treated as unquestioned ground truth. The original review text will serve as the primary source of evidence.

## 4. Research Questions

1. What user-reported concerns occur most frequently in MyChart reviews?
2. How do sentiment and recurring concerns differ across star-rating groups?
3. How do review volume and recurring concerns vary over time?
4. Are particular issues more prevalent in reviews associated with specific application versions, where sufficient data is available?
5. How can NLP and selective LLM-assisted extraction produce reliable, interpretable findings for digital health stakeholders?

These questions support decisions related to product improvement, technical investigation, customer support prioritization, and review-monitoring practices.

## 5. Analysis Approach

**Selected Path: Path B — Understanding and Extraction**

The project focuses on identifying and describing patterns in existing user reviews. It does not attempt to predict future failures, classify incoming reviews as an operational early-warning system, or establish causal relationships between application releases and user complaints.

### Phase II: Development and Exploratory Analysis

Planned activities include:

- Dataset quality and feasibility audit
- Descriptive statistics and missing-value analysis
- Rating and review-length distributions
- Text preprocessing
- Keyword and n-gram frequency analysis
- Baseline sentiment analysis
- Exploratory topic modeling, where relevant
- Historical review-pattern analysis
- App-version coverage assessment
- Interpretation of findings in relation to stakeholder decisions

### Phase III: Advanced Analysis and Integration

Planned activities include:

- Refinement of user-concern categories
- Selective use of Claude for contextual issue extraction
- Distinguishing actual complaints from praise, sarcasm, or neutral references
- Manual validation of extracted concerns
- Comparison of issue frequencies across ratings, time periods, and versions
- Development of stakeholder-facing summaries supported by counts, percentages, and representative reviews

Claude's role will be evaluated based on accuracy, consistency, token usage, processing cost, and privacy considerations.

## 6. Preliminary Concern Categories

The project will initially investigate:

- **Technical reliability:** Crashes, bugs, freezing, and loading problems
- **Medical-record and account access:** Login failures, authentication problems, and difficulty accessing information
- **Usability and accessibility:** Navigation difficulties, interface design, and accessibility barriers
- **Customer support:** Delayed responses, unresolved issues, and support experiences
- **Data accuracy and synchronization:** Missing, inaccurate, or unsynchronized information
- **Privacy and data control:** Data sharing, consent, permissions, and control over personal information

These are provisional categories. Their relevance and frequency will be assessed using the actual review text. Reviews may contain multiple concerns or none of the categories.

## 7. Interpretability and Limitations

The project defines interpretability primarily as **stakeholder-facing interpretability**.

Where supported by the data, important findings will include:

- Identified issue or theme
- Number and percentage of relevant reviews
- Comparison with an appropriate baseline
- Associated ratings, time periods, or app versions
- Representative supporting review excerpts
- Potential implications for product or customer-experience teams

The analysis will acknowledge limitations involving dataset representativeness, annotation reliability, sarcasm, sentiment-model errors, missing version information, and potential LLM inaccuracies.

Observed associations between app versions and complaints will not be presented as proof of causation.

## 8. Repository Organization

The intended repository structure is:

```text
HealthTrust-Watch/
├── README.md
├── PROJECT_PLAN.md
├── LICENSE
├── .gitignore
├── requirements.txt
├── data/
├── notebooks/
├── src/
└── outputs/
    └── figures/
```

The repository will be updated incrementally throughout Phase II and Phase III.

## 9. Project Status

**Current stage:** Phase II — Development and Exploratory Analysis

- Phase I: Initial project proposal and feedback received
- Phase II: Revised project scope, dataset audit, classical NLP analysis, and development checkpoint
- Phase III: Advanced issue extraction, validation, comparative analysis, and final stakeholder findings

The project documentation, code, and results will be updated as development progresses.

## 10. Project Goal

The final objective is to develop a reproducible, interpretable NLP analysis of MyChart user reviews that helps digital health stakeholders understand recurring user concerns, investigate historical patterns, and identify areas that may benefit from further product or service improvements.
