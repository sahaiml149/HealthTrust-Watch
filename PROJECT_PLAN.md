# HealthTrust Watch – Revised Project Plan

**Course:** INFO 4360 – NLP for Real-World Problems  
**Project:** HealthTrust Watch  
**Current Stage:** Phase II – Development and Exploratory Analysis  
**Analysis Path:** Path B – Understanding and Extraction

## 1. Project Objective

The objective of HealthTrust Watch is to apply Natural Language Processing (NLP) to identify, analyze, and interpret user-reported concerns in reviews of the MyChart healthcare application.

Following feedback from Phase I, the project has been refined from a multi-application privacy-focused early-warning concept into a single-application exploratory analysis of broader healthcare user experiences.

The revised scope includes technical reliability, medical-record access, usability, customer support, data accuracy, and privacy or data control.

The project aims to generate interpretable findings that can help digital health stakeholders understand recurring user concerns and prioritize areas for further investigation.

## 2. Problem Statement

Healthcare applications are increasingly used to access medical records, communicate with healthcare providers, and manage health-related services.

However, users may experience technical problems, difficulty accessing information, confusing interfaces, inadequate support, or concerns about their personal information.

These experiences are frequently expressed in unstructured application reviews. Manually analyzing large volumes of feedback can be time-consuming and may make it difficult to identify recurring patterns.

This project investigates how NLP techniques can organize and summarize historical MyChart reviews into meaningful themes and evidence-based insights.

The project does not aim to predict future application failures or establish causal relationships between software releases and user complaints.

## 3. Primary Stakeholders

**Primary Stakeholder:** Digital Health Product Manager

The product manager can use the findings to understand recurring concerns, identify potential usability or reliability problems, and prioritize areas requiring further investigation.

**Secondary Stakeholders:**

- **Customer Experience and Support Teams:** Identify recurring service issues and common user frustrations.
- **Engineering and Quality Assurance Teams:** Investigate technical reliability and application-version patterns.
- **Privacy and Data Governance Teams:** Examine credible concerns about personal information, consent, and data control.

## 4. Dataset and Scope

The project uses the Health App Reviews for Privacy & Trust (HARPT) dataset.

The original dataset includes reviews from multiple digital health applications. For this project, the analysis will focus on reviews associated with **MyChart**.

Relevant fields include:

- `content`: Original review text
- `score`: User-provided star rating
- `at`: Review date
- `app_name`: Application name
- `reviewCreatedVersion`: Application version, where available
- `trust_dimension`: Existing annotation, treated as unverified metadata

The first stage of Phase II will evaluate:

- Review count and duplicate records
- Missing and incomplete values
- Star-rating distribution
- Review-text length and quality
- Review-date coverage
- Application-version availability
- Representativeness and potential dataset biases

The final usable sample and feasibility of version-level comparisons will be determined from the actual data audit.

## 5. Revised Research Questions and Business Motivation

### RQ1: What user-reported concerns occur most frequently in MyChart reviews?

**Business motivation:** Product managers need to understand which problems are most commonly discussed so they can prioritize investigation and improvement efforts.

**Planned analysis:** Keyword frequencies, bigrams, exploratory topics, and review examples.

### RQ2: How do sentiment and recurring concerns differ across star-rating groups?

**Business motivation:** Customer-experience teams need to understand what distinguishes dissatisfied users from users reporting positive experiences.

**Planned analysis:** Baseline sentiment analysis, star-rating comparisons, and qualitative examination of representative reviews.

### RQ3: How do review volume and recurring concerns change over time?

**Business motivation:** Product and support teams can use historical comparisons to understand whether particular issues appear more frequently during certain periods.

**Planned analysis:** Monthly or quarterly review counts, sentiment trends, and issue-related keyword comparisons.

### RQ4: Are specific concerns more prevalent in reviews associated with particular application versions?

**Business motivation:** Engineering and quality-assurance teams may benefit from identifying versions that warrant further technical investigation.

**Planned analysis:** App-version completeness audit, review counts by version, and issue-frequency comparisons where sufficient data is available.

Version-associated differences will not be interpreted as evidence that a particular release caused the observed problems.

### RQ5: Can NLP and selective LLM-assisted extraction identify user concerns accurately and interpretably?

**Business motivation:** Product teams need reliable and understandable findings before using automated analysis to inform decisions.

**Planned analysis:** Classical NLP baselines, selective Claude-assisted issue extraction in Phase III, manual validation, and evidence-based summaries.

## 6. Selected Analysis Path

**Path B: Understanding and Extraction**

The project will focus on understanding historical review content, extracting relevant concerns, and comparing descriptive patterns.

Path B is appropriate because the primary stakeholder needs explanations of existing user experiences rather than predictions about future failures.

The project will not claim to operate as an automated early-warning system or predictive classifier.

If a predictive application is considered in future work, it would require a separately defined prediction target, validated labels, and appropriate model evaluation.

## 7. Phase II – Planned Development

### 7.1 Data Exploration

- Load and inspect the selected MyChart reviews.
- Evaluate missing values, duplicates, and data quality.
- Analyze rating distributions and review lengths.
- Examine representative positive, negative, and ambiguous reviews.
- Audit review dates and application-version coverage.

### 7.2 Text Mining

- Apply reusable text-cleaning and preprocessing functions.
- Analyze word frequencies and bigrams.
- Compare keywords across rating groups.
- Perform baseline sentiment analysis.
- Explore topic modeling where appropriate.
- Visualize patterns and explain their relevance to stakeholder decisions.

### 7.3 Preliminary Historical Analysis

- Examine review volume over time.
- Explore sentiment trends.
- Assess whether version-level comparisons are feasible.
- Identify potential limitations due to missing data and unequal sample sizes.

### 7.4 Phase III Preparation

- Define provisional issue categories.
- Document Claude's proposed role.
- Prepare sample prompts for issue extraction.
- Establish a manual validation strategy.
- Identify privacy, cost, scalability, and accuracy concerns.

## 8. Phase III – Planned Advanced Analysis

Phase III will build on the exploratory findings rather than replace them.

The team plans to:

1. Refine the concern categories based on observed review content.
2. Use Claude selectively to identify specific user-reported issues and supporting text.
3. Distinguish actual complaints from praise, neutral statements, and ambiguous references.
4. Allow multiple concerns per review and a no-issue classification.
5. Manually evaluate a sample of extracted results.
6. Compare validated concern frequencies across ratings, time periods, and application versions.
7. Present stakeholder-oriented findings supported by evidence.

The scope of Claude processing will depend on data quality, token usage, processing cost, and validation results.

## 9. Response to Phase I Feedback

### 9.1 Predictive Language and Analysis Path

**Concern:** The original title implied prediction or early warning, while the selected Path B was descriptive.

**Revision:** The project now explicitly focuses on exploratory NLP and historical issue extraction. Predictive and early-warning claims have been removed from the current objectives.

### 9.2 Reliability of Existing Labels

**Concern:** Existing trust-related labels may not accurately reflect genuine user complaints.

**Revision:** The original review text will be the primary source of evidence. Existing `trust_dimension` labels will be treated as reference metadata rather than verified ground truth.

Classical NLP analysis will be conducted independently of these annotations. Claude-assisted issue extraction will be manually validated before its results are used to support substantive findings.

### 9.3 Limited Privacy-Complaint Prevalence

**Concern:** Genuine privacy complaints may be too infrequent to support a privacy-centered project.

**Revision:** The project has been broadened to investigate user-reported technical reliability, account access, usability, support, data accuracy, and privacy or data control.

Privacy findings will be reported separately only when supported by sufficient evidence. The team will not assume that a review discussing personal information necessarily represents a privacy complaint.

### 9.4 Interpretability

**Concern:** The original project did not sufficiently explain what interpretability meant.

**Revision:** Interpretability is defined as stakeholder-facing output interpretability rather than model-mechanism explainability.

Important findings will, where feasible, include:

- Identified issue or theme
- Number and proportion of relevant reviews
- Appropriate comparison or historical baseline
- Relevant rating, time period, or app version
- Representative supporting review excerpts
- Potential implications for stakeholders

### 9.5 Application-Version Analysis

**Concern:** Available application-version information was not incorporated into the proposed analysis.

**Revision:** The team will evaluate `reviewCreatedVersion` completeness and review counts by version.

Where coverage and sample sizes are adequate, the team will investigate whether particular concerns appear more frequently in reviews associated with specific versions.

The analysis will remain observational and will not claim that a version caused a reported issue.

### 9.6 Business Motivation

**Concern:** Research questions were not sufficiently connected to stakeholder needs.

**Revision:** Each research question now identifies a stakeholder decision and the planned analysis supporting that decision.

Findings will be interpreted in relation to product improvement, support prioritization, engineering investigation, and privacy review.

### 9.7 GitHub and Repository Quality

**Concern:** The repository needed stronger organization, documentation, and hygiene.

**Revision:** The team will maintain a `.gitignore`, a `LICENSE`, and a `requirements.txt`, organize notebooks and reusable code, and commit work incrementally.

Both team members will contribute substantive changes using their own GitHub identities.

API keys and sensitive configuration files will not be committed.

## 10. Risks and Limitations

The project recognizes the following limitations:

- **Selection bias:** App-store reviewers may not represent all MyChart users.
- **Rating imbalance:** Some rating categories may contain substantially more reviews than others.
- **Annotation reliability:** Existing labels may contain errors or may not represent actual complaints.
- **Sentiment ambiguity:** Sarcasm, negation, and mixed opinions can produce incorrect sentiment predictions.
- **Issue overlap:** A single review may mention multiple concerns.
- **Missing version information:** Incomplete version metadata may restrict release-associated comparisons.
- **Temporal confounding:** Changes over time may reflect review volume, user behavior, or other factors rather than product changes alone.
- **LLM validity:** Claude may omit issues, infer unsupported concerns, or produce inconsistent classifications.
- **Privacy:** Review text may contain personal or health-related details that should not be unnecessarily exposed or sent to external services.
- **Processing cost:** Large-scale LLM analysis may require sampling or batching to control token usage and cost.

## 11. Expected Deliverables

### Phase II

- Working Python notebook with data exploration and text mining
- Descriptive statistics and visualizations
- Preliminary interpretation of findings
- Documented Phase III analysis path and tool choice
- Written development update in the notebook
- Updated GitHub repository with incremental commits
- Executed HTML notebook export

### Phase III

- Refined and validated concern extraction
- Advanced comparison of recurring user-reported issues
- Stakeholder-facing summaries and supporting evidence
- Final discussion of limitations and recommendations

## 12. Expected Outcome

HealthTrust Watch aims to produce a reproducible and interpretable NLP analysis of MyChart reviews that helps digital health product teams understand recurring user concerns, compare historical patterns, and identify areas requiring further investigation.

The final emphasis will be on **evidence-based understanding and practical stakeholder value**, rather than unsupported prediction or automated early-warning claims.
