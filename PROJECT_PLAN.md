# HealthTrust Watch – Revised Project Plan

**Course:** INFO 4360 – Complex Data Analytics  
**Project:** HealthTrust Watch  
**Current Stage:** Phase II – Exploratory Analysis Completed; Final Deliverable Verification  
**Analysis Path:** Path B – Understanding and Extraction  
**Application:** MyChart  
**Team Members:** Sahithi Busi and Bhargava

---

## 1. Project Objective

The objective of HealthTrust Watch is to apply Natural Language Processing (NLP) to identify, analyze, and interpret user-reported concerns in reviews of the MyChart healthcare application.

Following feedback from Phase I, the project was refined from a multi-application, privacy-focused early-warning concept into a single-application exploratory analysis of broader healthcare user experiences.

The revised scope includes technical reliability, medical-record and account access, usability, customer support, data accuracy, and privacy or data control.

The project aims to generate interpretable, evidence-based findings that can help digital health stakeholders understand recurring concerns and prioritize areas for further investigation.

The project follows **Path B: Understanding and Extraction**, focusing on historical patterns rather than predictive classification or operational early-warning systems.

## 2. Problem Statement

Healthcare applications are increasingly used to access medical records, communicate with healthcare providers, schedule appointments, and manage health-related services.

However, users may experience technical problems, difficulty accessing information, confusing interfaces, inadequate support, or concerns about their personal information.

These experiences are frequently expressed in unstructured application reviews. Manually analyzing large volumes of feedback can be time-consuming and may make it difficult to identify recurring patterns.

HealthTrust Watch investigates how classical NLP techniques and selective LLM-assisted extraction can organize and summarize historical MyChart reviews into meaningful themes and actionable insights.

The project does not aim to predict future application failures or establish causal relationships between software releases and user complaints.

## 3. Primary Stakeholders

**Primary Stakeholder: Digital Health Product Manager**

Product managers can use the findings to understand recurring user concerns, identify potential usability or reliability problems, and prioritize areas requiring further investigation.

**Secondary Stakeholders:**

- **Customer Experience and Support Teams:** Identify recurring service issues and common user frustrations.
- **Engineering and Quality Assurance Teams:** Investigate technical reliability and application-version patterns.
- **Privacy and Data Governance Teams:** Examine credible concerns about personal information, consent, and data control.

The analysis emphasizes findings that stakeholders can interpret through issue frequencies, supporting review examples, rating comparisons, historical patterns, and appropriate limitations.

## 4. Dataset and Scope

The project uses the **Health App Reviews for Privacy & Trust (HARPT)** dataset.

The original dataset contains **480,450 reviews across 67 digital health applications**, covering approximately 2011–2025.

Following the revised project scope, the analysis focuses exclusively on MyChart reviews.

### 4.1 Dataset Preparation Results

| Dataset Stage | Number of Reviews |
|---|---:|
| Original HARPT dataset | 480,450 |
| MyChart subset | 93,392 |
| Removed due to missing or unusable review text | 46 |
| Final cleaned MyChart dataset | 93,346 |

The cleaned dataset retains approximately **99.95% of the original MyChart subset**.

These counts were verified through the executed Phase II notebook.

### 4.2 Relevant Dataset Fields

- `content`: Original review text
- `score`: User-provided star rating
- `at`: Review date
- `app_name`: Application name
- `reviewCreatedVersion`: Application version, where available
- `trust_dimension`: Existing annotation, treated as unverified reference metadata

### 4.3 Data Quality Assessment

Phase II examined:

- Review counts and missing values
- Duplicate records and text quality
- Star-rating distribution
- Review lengths
- Review-date coverage
- Application-version completeness
- Dataset limitations and potential representativeness concerns

The original review text serves as the primary source of evidence.

Existing `trust_dimension` labels are not treated as verified ground truth because some annotations may be inaccurate or inconsistent with the underlying reviews.

The full HARPT dataset is excluded from the public GitHub repository and must be obtained separately to reproduce the complete analysis.

## 5. Revised Research Questions and Business Motivation

### RQ1: What user-reported concerns occur most frequently in MyChart reviews?

**Business Motivation:** Product managers need to understand which problems users discuss most frequently so they can prioritize investigation and improvement efforts.

**Analysis:** Keyword frequencies, bigrams, exploratory topic modeling, and representative review examples.

### RQ2: How do sentiment and recurring concerns differ across star-rating groups?

**Business Motivation:** Customer-experience teams need to understand what distinguishes dissatisfied users from those reporting positive experiences.

**Analysis:** Baseline VADER sentiment analysis, rating-group comparisons, and qualitative examination of representative reviews.

### RQ3: How do review volume and recurring concerns change over time?

**Business Motivation:** Product and support teams can use historical comparisons to understand whether particular issues appear more frequently during certain periods.

**Analysis:** Monthly or quarterly review counts, sentiment trends, and issue-related keyword comparisons.

### RQ4: Are specific concerns more prevalent in reviews associated with particular application versions?

**Business Motivation:** Engineering and quality-assurance teams may benefit from identifying versions that warrant further technical investigation.

**Analysis:** App-version completeness assessment, review counts by version, and issue-frequency comparisons where sufficient data is available.

Version-associated differences will not be interpreted as evidence that a particular software release caused the observed problems.

### RQ5: Can NLP and selective LLM-assisted extraction identify user concerns accurately and interpretably?

**Business Motivation:** Product teams need reliable and understandable findings before using automated analysis to inform decisions.

**Analysis:** Classical NLP baselines completed during Phase II, followed by selective Claude-assisted issue extraction, manual validation, and evidence-based summaries during Phase III.

## 6. Selected Analysis Path

**Path B: Understanding and Extraction**

The project focuses on understanding historical review content, extracting relevant concerns, and comparing descriptive patterns.

Path B was selected because the primary stakeholder needs explanations of existing user experiences rather than predictions about future failures.

The project does not claim to operate as an automated early-warning system or predictive classifier.

A future predictive application would require a separately defined prediction target, validated labels, appropriate training and testing procedures, and model-performance evaluation.

## 7. Phase II – Completed Development and Exploratory Analysis

Phase II established the project's analytical foundation through data preparation, classical NLP, descriptive analysis, and feasibility assessment.

### 7.1 Data Exploration and Preparation

Completed activities include:

- Loading and inspecting the HARPT dataset
- Selecting MyChart reviews
- Evaluating missing and unusable review text
- Preparing the cleaned dataset of 93,346 reviews
- Examining rating distributions and review lengths
- Assessing review-date and application-version coverage
- Identifying data-quality limitations

### 7.2 Classical NLP and Text Mining

The Phase II notebook includes:

- Text preprocessing
- Word-frequency analysis
- Bigram analysis
- TF-IDF-based text representation
- Exploratory NMF topic modeling
- Baseline VADER sentiment analysis
- Rating-related comparisons
- Supporting visualizations and interpretation

These techniques establish exploratory baselines for understanding review content before introducing LLM-assisted extraction.

### 7.3 Historical and Application-Version Analysis

Phase II also examined:

- Historical review-volume patterns
- Sentiment trends
- Application-version availability
- Exploratory comparisons across application versions
- Limitations arising from unequal review counts and incomplete metadata

The analysis is descriptive and observational.

It does not establish that a particular software release caused an increase or decrease in complaints.

### 7.4 Preliminary Phase II Findings

The executed Phase II notebook produced the following preliminary results:

**Dataset Size and Retention**

The cleaned MyChart dataset contains 93,346 reviews, representing approximately 99.95% of the original MyChart subset.

**Rating Distribution**

Approximately 69.55% of cleaned reviews have five-star ratings, indicating a substantial imbalance toward positive ratings.

This imbalance must be considered when interpreting sentiment and comparing user concerns across rating groups.

**Review Length**

The median review length is approximately 12 words.

Short reviews may provide limited context for topic identification, sentiment interpretation, and issue extraction.

**Sentiment and Topic Exploration**

VADER sentiment analysis and exploratory topic modeling were successfully executed.

These methods provide initial perspectives on user experiences but do not independently establish the prevalence of validated complaint categories.

**Application-Version Availability**

Application-version information is available for approximately 91.38% of reviews.

This supports further exploratory version-associated comparisons, subject to sample-size and metadata-quality limitations.

### 7.5 Phase III Preparation

Phase II documented the proposed advanced-analysis approach, including:

- Provisional user-concern categories
- Claude's proposed role in contextual issue extraction
- Initial prompt-design considerations
- Human-validation methodology
- Privacy and API-security considerations
- Processing-cost and scalability considerations

Actual Claude API extraction and validation remain Phase III activities.

## 8. Phase III – Planned Advanced Analysis

Phase III will build on the exploratory findings rather than replace them.

The team plans to:

1. Refine the concern categories using observed MyChart review content.
2. Use Claude selectively to identify specific user-reported issues and supporting text.
3. Distinguish actual complaints from praise, neutral statements, sarcasm, and ambiguous references.
4. Allow multiple concerns per review and a no-issue classification.
5. Manually evaluate a sample of extracted results.
6. Assess extraction accuracy, consistency, and category-level performance.
7. Compare validated concern frequencies across ratings, time periods, and application versions.
8. Present stakeholder-oriented findings supported by counts, percentages, historical baselines, and representative review excerpts.

### 8.1 Provisional Concern Categories

- **Technical Reliability:** Crashes, bugs, freezing, and loading problems
- **Medical-Record and Account Access:** Login failures, authentication problems, and difficulty accessing records
- **Usability and Accessibility:** Navigation difficulties, interface design, and accessibility barriers
- **Customer Support:** Delayed responses, unresolved issues, and support experiences
- **Data Accuracy and Synchronization:** Missing, inaccurate, or unsynchronized information
- **Privacy and Data Control:** Data sharing, consent, permissions, and control over personal information

These categories remain provisional and will be refined through empirical review analysis.

### 8.2 Claude API Integration

Claude API integration is planned for Phase III.

Its role will be contextual issue extraction rather than replacing the classical NLP analysis.

The implementation will include:

- A defined extraction prompt and category descriptions
- Structured responses suitable for analysis
- Controlled sampling or batching
- Manual validation against human-reviewed examples
- Assessment of false positives, false negatives, and ambiguous cases
- Token-usage and cost monitoring
- Review of privacy and data-handling risks

API credentials will be stored outside the public repository using environment variables or other secure configuration mechanisms.

Only review content appropriate for external processing will be submitted to the API, with potentially sensitive personal information handled carefully.

### 8.3 Expected Phase III Outputs

The intended outputs include:

- Refined concern taxonomy
- Validated issue-extraction results
- Concern-frequency comparisons
- Rating, time-period, and version-related analyses
- Representative supporting evidence
- Stakeholder-facing summaries
- Evaluation of limitations and potential biases

The scope of Claude processing will depend on data quality, token usage, processing cost, and validation results.

## 9. Response to Phase I Feedback

### 9.1 Predictive Language and Analysis Path

**Concern:** The original project title implied prediction or early warning, while the proposed analysis was primarily descriptive.

**Revision:** The project now explicitly follows Path B and focuses on exploratory NLP and historical issue extraction.

Predictive and operational early-warning claims have been removed from the current objectives.

### 9.2 Reliability of Existing Labels

**Concern:** Existing trust-related annotations may not accurately represent genuine user complaints.

**Revision:** The original review text is treated as the primary source of evidence.

The existing `trust_dimension` field is used only as unverified metadata.

Classical NLP analysis is conducted independently of these annotations, and Claude-assisted extraction will require manual validation before supporting substantive findings.

### 9.3 Limited Privacy-Complaint Prevalence

**Concern:** Genuine privacy complaints may be too infrequent to support a privacy-centered project.

**Revision:** The project now investigates broader user-reported concerns involving technical reliability, account access, usability, support, data accuracy, and privacy or data control.

Privacy findings will be reported separately only when supported by sufficient evidence.

The project does not assume that every mention of personal information constitutes a privacy complaint.

### 9.4 Interpretability

**Concern:** The original project did not clearly define interpretability.

**Revision:** Interpretability is defined primarily as **stakeholder-facing output interpretability**, rather than model-mechanism explainability.

Where feasible, important findings will include:

- Identified issue or theme
- Number and percentage of relevant reviews
- Appropriate historical or comparative baseline
- Associated rating, time period, or application version
- Representative supporting review excerpts
- Potential implications for stakeholders

### 9.5 Application-Version Analysis

**Concern:** Available application-version information was not incorporated into the original plan.

**Revision:** Phase II evaluated version-field completeness and explored version-related patterns.

Phase III will investigate validated concern frequencies across versions where sufficient data is available.

The analysis will remain observational and will not claim that particular versions caused the reported issues.

### 9.6 Business Motivation

**Concern:** Research questions were not sufficiently connected to stakeholder needs.

**Revision:** Each research question now identifies its business motivation and corresponding analytical approach.

Findings will be interpreted in relation to product improvement, customer support prioritization, engineering investigation, and privacy review.

### 9.7 GitHub and Repository Quality

**Concern:** The repository required stronger documentation, organization, and security practices.

**Revision:** The repository includes:

- `.gitignore`
- MIT `LICENSE`
- `requirements.txt`
- `README.md`
- `PROJECT_PLAN.md`
- Data and notebook directories

The README documents dataset preparation, setup instructions, and reproducibility guidance.

Both team members contributed commits under their respective Git identities.

Phase II documentation improvements were merged into `main` through Pull Request #2.

API keys and sensitive configuration files are excluded from version control.

## 10. Risks and Limitations

The project recognizes the following limitations:

- **Selection Bias:** App-store reviewers may not represent all MyChart users.
- **Rating Imbalance:** Positive ratings substantially outnumber some negative-rating categories.
- **Annotation Reliability:** Existing labels may contain errors or fail to represent actual complaints.
- **Sentiment Ambiguity:** Sarcasm, negation, and mixed opinions can produce incorrect sentiment predictions.
- **Issue Overlap:** A single review may mention multiple concerns.
- **Short Review Text:** Brief reviews may lack sufficient context for reliable classification.
- **Missing Version Information:** Incomplete metadata may restrict release-associated comparisons.
- **Temporal Confounding:** Historical changes may reflect review volume, user behavior, or other factors rather than product changes alone.
- **LLM Validity:** Claude may omit issues, infer unsupported concerns, or produce inconsistent classifications.
- **Privacy:** Review text may contain personal or health-related details that should not be unnecessarily exposed or sent to external services.
- **Processing Cost:** Large-scale LLM analysis may require sampling or batching to control token usage and cost.

These limitations will be considered when interpreting findings and developing stakeholder recommendations.

## 11. Project Deliverables and Status

### Phase I – Completed

- Initial project proposal
- Professor feedback received
- Revised project scope and analysis path

### Phase II – Exploratory Analysis Completed

**Completed and verified:**

- Working Python notebook containing data exploration and text mining
- Data cleaning and descriptive statistics
- Exploratory visualizations and NLP analyses
- Preliminary interpretation of findings
- Documented Phase III methodology and tool-selection rationale
- Updated GitHub documentation
- Incremental commits attributed to both contributors
- Successful notebook execution without recorded cell errors
- Installation and verification of required NLP dependencies

**Final deliverable checks:**

- Confirm that the executed HTML notebook export is generated and included in the submission.
- Confirm that the submitted materials satisfy all Phase II instructions.
- Confirm that the README, project plan, and notebook are consistent.

### Phase III – Planned

- Refined and validated concern extraction
- Claude API-assisted contextual analysis
- Manual validation and extraction evaluation
- Advanced comparisons of recurring user-reported issues
- Stakeholder-facing summaries and supporting evidence
- Final discussion of limitations, biases, and recommendations
- Final project presentation and report

## 12. Reproducibility and Repository Management

The project repository contains the documentation, dependency declarations, and analytical notebook needed to reproduce the Phase II workflow.

The complete analysis requires access to the original HARPT dataset, which is not included in the public repository.

The README provides setup instructions for installing dependencies and executing the notebook.

The team will maintain version control, document significant methodological changes, and avoid committing API credentials or sensitive information.

The Phase II notebook has been executed successfully in the current development environment. Independent execution in a clean environment remains a separate reproducibility check.

## 13. Expected Outcome

HealthTrust Watch aims to produce a reproducible and interpretable NLP analysis of MyChart reviews that helps digital health product teams understand recurring user concerns, compare historical patterns, and identify areas requiring further investigation.

The final emphasis is on **evidence-based understanding, transparent methodology, validated issue extraction, and practical stakeholder value**, rather than unsupported prediction or automated early-warning claims.

The completed Phase II exploratory analysis establishes the foundation for Phase III, where selective Claude-assisted extraction and manual validation will support more specific, reliable, and actionable findings.