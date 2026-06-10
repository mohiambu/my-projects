# README

## Project Title

Unsupervised Anomaly Detection for Pill Defect Identification

## Group Members

* Mohammed Ambusaidi

## Project Summary

This project studies pill defect detection using the MVTec AD pill dataset. The goal was to identify defective pill images using unsupervised anomaly detection methods.

The models were trained only on normal pill images and tested on both normal and defective pill images. Several machine learning methods were evaluated, including:

* Isolation Forest
* One-Class SVM
* Local Outlier Factor (LOF)
* PCA Reconstruction Error

The final model combined LOF and PCA using a weighted hybrid score and achieved the best performance.

## Final Results

* ROC-AUC: 0.8783
* Accuracy: 87.43%
* Defect Recall: 95.74%

## Files Included

### Report

* `CV_Final_PDF.pdf`
  Final project report.

### Code

* `CV_Final_Code.ipynb`
  Google Colab notebook containing preprocessing, model training, evaluation, and plots.

### Dataset

* MVTec AD Pill Dataset
  Used for training and testing.

Note: The MVTec AD pill dataset is not included in this submission because of file size limitations.
The dataset can be downloaded from the official MVTec website: https://www.mvtec.com/research-teaching/datasets/mvtec-ad

## How to Run

1. Open the notebook file in Google Colab. 

2. Install required libraries if needed:
   * Python 3
   * NumPy
   * OpenCV
   * scikit-learn
   * matplotlib
3. Download and extract the MVTec AD pill dataset.
4. Update dataset paths inside the notebook.
5. Run cells in order.

## Notes

* Training uses only normal pill images.
* Testing uses both normal and defective pill images.
* Figures in the report were generated from notebook outputs.

## References

See the report PDF for full references.
