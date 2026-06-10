# Cybersecurity Beaconing Detection

## Overview

This project was completed as part of the IU OmniSOC Capstone Project. The goal was to detect command-and-control (C2) beaconing activity in network traffic using machine learning.

C2 beaconing happens when infected devices communicate with external servers at regular intervals. These patterns can be difficult to identify because they often look similar to normal network traffic.

## Project Goal

The main objectives were to:

- Detect suspicious beaconing behavior
- Separate attack traffic from normal traffic
- Reduce false positives
- Help security analysts focus on high-risk activity

## Dataset

The project used the CTU-13 network traffic dataset, which contains both normal and malicious traffic.

The data included:

- Network flow records
- Timing information
- Packet sizes
- Connection duration
- Traffic statistics

To improve performance, over 30 additional features were created from the original data.

## Methods

Several anomaly detection models were tested:

- Isolation Forest (IF1)
- Isolation Forest (IF2)
- One-Class SVM (OCSVM)

The final model combined all three methods into a weighted ensemble to produce a single anomaly score.

## Model Workflow

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

### Performance Metrics

- ROC-AUC: **0.973**
- KS Statistic: **0.863**
- Stable performance across **20 runs**
- Captured approximately **90% of attacks within the top 10% of anomaly scores**

### Key Findings

- The final ensemble model performed better than a single Isolation Forest model.
- Feature engineering improved the separation between normal and attack traffic.
- The model consistently ranked suspicious traffic near the top, making investigation easier for analysts.

## Technologies Used

- Python
- Scikit-learn
- NumPy
- Pandas
- Matplotlib

## Visual Results

### Baseline Model

![Baseline Model](baseline_model.png)

### Final Ensemble Model

![Final Model](final_model.png)

The final model shows much better separation between normal and attack traffic, making malicious activity easier to identify.

## Future Improvements

- Test on real-world OmniSOC traffic
- Integrate with Elastic SIEM
- Reduce false positives further
- Explore deep learning approaches

## Note

This project was completed as part of an IU OmniSOC capstone project. Due to project restrictions, the source code and data are not publicly available.
