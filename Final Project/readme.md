# ANA 675 – Final Project

## Predictive Maintenance Using Machine Learning and Neural Networks

**Author:** Randall C. Crawford
**Course:** ANA 675 – Neural Networks & Deep Learning

---

## Project Overview

This project explores **predictive maintenance modeling** using a synthetic dataset designed to reflect real-world industrial manufacturing conditions. The objective was to **evaluate and compare traditional machine learning models with neural network approaches** for detecting rare machine failures under class imbalance and non-linear process constraints.

Rather than focusing solely on model accuracy, the project emphasized **model suitability, interpretability, and failure-mode alignment**, which are critical in industrial predictive maintenance settings.

---

## Dataset

* **Source:** AI4I 2020 Predictive Maintenance Dataset (UCI Machine Learning Repository)
* **Samples:** 10,000
* **Features:** Sensor readings, process parameters, and product quality indicators
* **Target:** Binary machine failure (Pass / Fail)
* **Class Imbalance:** ~3.39% failures

The dataset includes **five independent failure mechanisms**, each governed by distinct physical constraints, making it ideal for comparing model behavior across rule-based and continuous optimization approaches.

---

## Feature Engineering

To better reflect the underlying failure mechanisms, multiple **engineered features** were introduced:

* Temperature difference for heat dissipation failure
* Rotational speed converted to radians per second
* Power derived from torque and rotational speed
* Tool wear–torque interaction for overstrain failure
* Encoded product quality type

Feature selection was guided by **domain logic**, statistical behavior, and alignment with known failure conditions rather than blind dimensionality reduction.

---

## Modeling Approach

### Machine Learning Models

* **Decision Tree (class-weighted, tuned depth)**
* **Random Forest (balanced class weights, ensemble learning)**

Tree-based models proved highly effective due to the **threshold-driven nature of the failure modes**, achieving strong precision–recall balance for rare failures.

### Neural Network Models

* **Artificial Neural Network (ANN)** with:

  * Multiple hidden layers
  * Dropout regularization
  * Class-weighted loss
  * Threshold optimization for F1-score

Recurrent models (RNN/LSTM) were explored but ultimately ruled out due to **non-stationary sequencing caused by mixed product types**, which degraded performance.

---

## Model Evaluation

Models were evaluated using:

* Accuracy
* Precision, Recall, and **F1-score (primary metric)**
* ROC-AUC
* Confusion matrices

The **Random Forest classifier** outperformed the ANN in detecting minority-class failures, demonstrating that **ensemble tree methods are better suited to rule-based failure structures** than gradient-based neural optimization in this context.

---

## Key Findings

* Tree-based models align naturally with **conditional, threshold-driven failure mechanisms**
* Neural networks struggled to isolate rare failures despite class weighting
* Feature engineering grounded in **process physics** outperformed purely statistical approaches
* Model interpretability is critical in maintenance applications where false negatives are costly

---

## Tools & Technologies

* **Python**
* **scikit-learn**
* **TensorFlow / Keras**
* NumPy, Pandas, Matplotlib, Seaborn

---

## Outcome

This project demonstrates the ability to:

* Translate industrial process knowledge into analytic features
* Select models based on **problem structure**, not trend
* Evaluate machine learning and neural networks under **severe class imbalance**
* Communicate results in a way suitable for **real manufacturing decision-making**

---

