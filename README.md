# HealthTrust Watch

## NLP-Based Early-Warning System for Privacy and Trust Concerns in Digital Health Apps

HealthTrust Watch is an INFO 4360 course project that explores how Natural Language Processing (NLP) can be used to identify emerging privacy, trust, and reliability concerns in digital health application reviews.

### Problem

Digital health applications such as patient portals and telehealth platforms receive large volumes of user feedback. Important concerns involving application reliability, privacy, data control, and trust may be difficult for product teams to identify quickly through manual review.

This project aims to develop an NLP-based early-warning framework that transforms unstructured health-app reviews into structured privacy and trust signals and examines how these concerns vary across applications and over time.

### Stakeholder

The primary stakeholder is a Digital Health Product Risk or Trust & Safety Manager responsible for monitoring user concerns and identifying issues that may require further investigation.

### Dataset

The project uses the Health App Reviews for Privacy & Trust (HARPT) dataset.

The primary dataset contains 480,450 reviews from 67 digital health applications covering 2011–2025. The applications include patient portals and telehealth platforms.

Key fields used in the project include:

- Review text
- Star rating
- Application name
- Review date/year
- Application type
- Trust dimension
- Model confidence score

A separate ground-truth dataset is also available to support validation and exploration.

### Analysis Approach

The primary project approach is Path B: Understanding/Extraction.

Planned analysis may include:

- Keyword and n-gram analysis
- Sentiment analysis
- Topic discovery
- Comparison of concerns across applications and app types
- Temporal analysis of privacy and trust concerns
- Detection of unusual increases in specific concerns

The Claude API may be used selectively for tasks such as interpreting topic clusters or extracting structured issue descriptions where contextual interpretation adds value.

### Project Goal

The final goal is to develop an interpretable early-warning framework that helps identify app-, issue-, and time-specific patterns that may warrant further investigation by digital health product teams.
