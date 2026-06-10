# Cybersecurity Beaconing Detection for Command-and-Control (C2) Traffic

## Overview

This project was completed as part of the IU OmniSOC Capstone Project. The goal was to detect command-and-control (C2) beaconing activity in network traffic using unsupervised machine learning techniques.

C2 beaconing occurs when compromised systems communicate with external servers at regular intervals. Because beaconing traffic often resembles normal network activity, it can be difficult to detect using traditional methods.

This project developed an ensemble anomaly detection framework that assigns anomaly scores to network flows, helping analysts identify suspicious communication patterns.

---

## Objectives

- Detect C2 beaconing behavior using anomaly detection
- Distinguish malicious traffic from normal traffic
- Reduce false positives and improve ranking reliability
- Provide stable and interpretable anomaly scores for cybersecurity analysts

---

## Dataset

### CTU-13 Dataset

The project used the CTU-13 botnet dataset, which contains labeled network traffic with both normal and malicious activity.

Dataset characteristics:

- Approximately 56,000 network flows
- Roughly 5% attack traffic
- Statistical network flow features including:
  - Timing information
  - Packet sizes
  - Duration
  - Traffic ratios

---

## Feature Engineering

To improve detection performance, more than 30 additional features were engineered, including:

- Timing regularity metrics
- Traffic asymmetry measures
- Communication frequency indicators
- Statistical flow summaries

Data preprocessing included:

- Cleaning and filtering
- Feature scaling
- Yeo-Johnson transformation

---

## Methodology

### Baseline Model

- Isolation Forest

### Improved Models

- Isolation Forest (IF1)
- Isolation Forest (IF2)
- One-Class SVM (OCSVM)

### Final Ensemble

The final anomaly score was generated using a weighted ensemble of:

- IF1
- IF2
- OCSVM

The model weights were optimized to maximize separation between normal and attack traffic while maintaining stability across multiple runs.

---

## Model Pipeline

```text
CTU-13 Data
      ↓
Feature Engineering
      ↓
IF1 + IF2 + OCSVM
      ↓
Final Anomaly Score
```

## Results

| Metric | Value |
|----------|----------|
| ROC-AUC | 0.973 |
| KS Statistic | 0.863 |
| Separation Score | ~0.37 |
| Stability | Consistent across 20 runs |
| Attack Capture Rate | ~90% of attacks within top 10% anomaly scores |

### Key Findings

- Significant improvement over the baseline Isolation Forest model
- Strong separation between normal and malicious traffic
- Stable anomaly scores suitable for operational use
- Effective prioritization of high-risk network activity

---

## Technologies Used

- Python
- Scikit-learn
- NumPy
- Pandas
- Matplotlib

---

## Future Work

- Test on real IU OmniSOC traffic
- Integrate into Elastic SIEM pipelines
- Improve attack precision and reduce false positives
- Explore clustering and deep learning approaches

---

## Project Context

This work was completed as part of the Indiana University OmniSOC Capstone Project.

**Supervisor:** Scott Orr (IU OmniSOC)

**Students:** Mohammed Ambusaidi, Nolan Knies

---

## Note

Due to project restrictions and cybersecurity considerations, the source dataset and implementation code are not publicly available. This repository provides a summary of the methodology and results.
