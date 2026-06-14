# Transmission Line Fault Classification using Machine Learning

Machine learning-based classification of transmission line faults using electrical measurements obtained from the IEEE Dataport repository. This project presents a comparative analysis of multiple classification algorithms to identify the most effective approach for fault diagnosis in power transmission systems. The study evaluates nine machine learning models using a large-scale dataset containing **578,923 records**, highlighting the potential of data-driven techniques in modern power system protection.

---

## Overview

Reliable fault detection and classification are critical for ensuring the stability, safety, and efficient operation of electrical power systems. Traditional protection schemes often rely on predefined thresholds and rule-based approaches, which may struggle to adapt to the complex and nonlinear nature of transmission line faults.

This project investigates the application of machine learning techniques for the classification of transmission line faults using voltage and current measurements. Multiple classification algorithms were trained and evaluated on a real-world dataset obtained from **IEEE Dataport**, enabling a comprehensive comparison of their performance in identifying different fault conditions.

The objective was not only to achieve high classification accuracy but also to understand the strengths and limitations of different machine learning models when applied to power system protection problems.

---

## Objectives

* Develop machine learning models for transmission line fault classification.
* Compare the performance of multiple classification algorithms.
* Evaluate the impact of class imbalance and resampling techniques.
* Identify the most suitable model for fault diagnosis applications.
* Demonstrate the applicability of machine learning in power system protection.

---

## Fault Categories Considered

The dataset included the following transmission line conditions:

| Fault Type | Description                 |
| ---------- | --------------------------- |
| No Fault   | Normal operating condition  |
| LG         | Line-to-Ground Fault        |
| LL         | Line-to-Line Fault          |
| LLG        | Double Line-to-Ground Fault |
| LLLG       | Three-Phase Fault           |

---

## Dataset Information

* **Dataset Source:** IEEE Dataport
* **Total Records:** 578,923
* **Features:** 45 attributes
* **Input Variables:**

  * Phase voltages (Va, Vb, Vc)
  * Phase currents (Ia, Ib, Ic)
  * Derived electrical parameters
* **Target Variable:**

  * Fault classification category

The dataset exhibited significant class imbalance, with the majority of observations corresponding to the **No Fault** condition.

### Class Distribution Before SMOTE

| Class    | Approximate Distribution |
| -------- | ------------------------ |
| No Fault | 73%                      |
| LG       | 8%                       |
| LL       | 7%                       |
| LLG      | 7%                       |
| LLLG     | 5%                       |

---

## Data Preprocessing

The following preprocessing steps were performed:

* Dataset loading and inspection
* Handling categorical labels
* Label encoding of fault categories
* Train-test split
* Feature scaling (where applicable)
* Analysis of class imbalance
* Synthetic Minority Oversampling Technique (SMOTE) for balancing the training dataset

The test dataset was intentionally left unchanged to preserve real-world class distributions and ensure an unbiased evaluation.

---

## Machine Learning Models Evaluated

The following classification algorithms were implemented and compared:

1. Logistic Regression
2. Logistic Regression with SMOTE
3. Linear Support Vector Classifier (LinearSVC)
4. Gaussian Naïve Bayes
5. K-Nearest Neighbors (KNN)
6. Multi-Layer Perceptron (MLP) Classifier
7. Decision Tree
8. Gradient Boosting
9. AdaBoost
10. Random Forest

---

## Performance Evaluation Metrics

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix Analysis

These metrics provided a comprehensive assessment of each model's ability to classify transmission line faults correctly.

---

## Experimental Results

### Comparative Model Performance

| Model                       | Accuracy (%) | Performance Summary                         |
| --------------------------- | ------------ | ------------------------------------------- |
| Logistic Regression         | 88.06        | Majority class bias observed                |
| Logistic Regression (SMOTE) | 31.40        | Improved recall but poor precision          |
| LinearSVC                   | 88.08        | Limited by linear decision boundaries       |
| Gaussian Naïve Bayes        | 66.23        | Moderate performance                        |
| KNN                         | 96.88        | Strong performance, slower inference        |
| MLP Classifier              | 96.83        | High accuracy with tuning sensitivity       |
| Decision Tree               | 97.92        | Excellent performance with interpretability |
| Gradient Boosting           | 95.40        | Strong ensemble performance                 |
| AdaBoost                    | 97.98        | Exceptional minority-class recall           |
| **Random Forest**           | **97.99**    | **Best overall performer**                  |

---

## Key Findings

* Ensemble methods significantly outperformed linear classifiers.
* Random Forest achieved the highest overall performance across all evaluation metrics.
* AdaBoost demonstrated excellent minority-class detection capabilities.
* Decision Trees offered an effective balance between accuracy and interpretability.
* Linear models struggled to capture the nonlinear characteristics of transmission line fault signatures.
* SMOTE influenced different model families differently, improving recall in some cases while reducing overall accuracy in others.

---

## Software Tools and Libraries

### Development Environment

* Python 3.x
* Google Colab
* Jupyter Notebook

### Libraries Used

* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* imbalanced-learn (SMOTE)
* Joblib

---

## Project Structure

```text
transmission-line-fault-classification-using-machine-learning/
│
├── README.md
│
├── notebooks/
│   └── transmission_line_fault_classification.ipynb
│
├── presentation/
│   └── Transmission_Line_Fault_Classification.pptx
│
├── references/
│   ├── reference_1.pdf
│   ├── reference_2.pdf
│   └── bibliography.md
│
├── results/
│   ├── confusion_matrices/
│   ├── accuracy_comparison.png
│   └── model_performance_summary.csv
│
└── dataset/
    └── dataset_source.txt
```

---

## How to Run the Project

1. Clone the repository.

```bash
git clone https://github.com/yourusername/transmission-line-fault-classification-using-machine-learning.git
```

2. Install the required dependencies.

```bash
pip install numpy pandas matplotlib seaborn scikit-learn imbalanced-learn joblib
```

3. Open the Jupyter Notebook.

```bash
jupyter notebook
```

4. Run the notebook cells sequentially to reproduce the analysis and results.

---

## Applications

* Intelligent power system protection
* Automated fault diagnosis
* Smart grid monitoring systems
* Decision support systems for utilities
* Research in AI applications for electrical engineering

---

## Limitations

* The dataset was obtained from an IEEE research repository rather than a live operational power grid.
* Hyperparameter tuning was performed through manual experimentation rather than exhaustive optimization.
* Real-time deployment and embedded implementation were not investigated.
* The models were not tested under extreme environmental conditions or sensor failures.

---

## Future Work

Potential extensions of this work include:

* Deep learning approaches using LSTM and CNN architectures.
* Real-time fault monitoring pipelines.
* IoT-enabled deployment for smart substations.
* Automated feature importance analysis using SHAP.
* Joint fault classification and fault location estimation.
* Embedded implementation for edge-based fault diagnosis.

---

## Educational Outcomes

This project provided practical experience in:

* Machine learning model development
* Classification problem solving
* Power system fault analysis
* Large-scale dataset processing
* Handling imbalanced datasets
* Comparative evaluation of ML algorithms
* Research methodology and literature review
* Data visualization and interpretation
* Technical presentation and documentation

---

## References

1. IEEE Dataport – Transmission Line Fault Dataset
2. Abniki et al., *An ANN-Impedance-based Fault Detection Technique in T-Connection Transmission Overhead Lines*, IEEE, 2012.
3. Yamuna and Thresia, *Fault Detection in Transmission Lines using Summation of Squared Three-Phase Currents*, 2022.
4. Huang, *Transmission Line Faults Classification Based on Alienation Coefficients of Current and Voltage Waveform and SVM*, 2023.
5. Additional references are available in the `references/` directory.

---

## Conclusion

This project demonstrates the effectiveness of machine learning techniques in the classification of transmission line faults using voltage and current measurements. Through a rigorous comparison of multiple algorithms, ensemble methods—particularly **Random Forest**—emerged as highly reliable solutions for fault diagnosis tasks. The findings highlight the potential of integrating machine learning into future power system protection frameworks, contributing to the development of more intelligent, adaptive, and resilient electrical grids.
