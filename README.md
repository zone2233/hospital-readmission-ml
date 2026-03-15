# Hospital Readmission Prediction (Decision Tree vs Random Forest)

This project was developed as part of a machine learning assignment to compare Decision Tree and Random Forest models for predicting hospital readmissions.

## Project Overview

This project applies machine learning techniques to predict whether a hospital patient will be **readmitted within 30 days** based on clinical and administrative data.

The goal is to compare two models:

- Decision Tree Classifier
- Random Forest Classifier

The comparison highlights the differences between a **single interpretable model** (Decision Tree) and an **ensemble model** (Random Forest) that generally provides better predictive performance.

---

## Dataset

The dataset used in this project comes from Kaggle:

https://www.kaggle.com/datasets/siddharth0935/hospital-readmission-predictionsynthetic-dataset

Download the dataset and place it in the `data/` folder before running the notebook.

The dataset contains approximately **30,000 hospital records** and includes features such as:

- Age
- BMI
- Cholesterol level
- Diabetes status
- Length of hospital stay
- Medication count
- Discharge destination

The target variable is:

**readmitted_30_days**
- `Yes` → patient was readmitted within 30 days
- `No` → patient was not readmitted

---

## Methods

The following steps were performed:

1. Data loading and inspection
2. Data preprocessing
   - Removing unnecessary columns
   - Encoding categorical variables
3. Train-test split (80/20)
4. Training models:
   - Decision Tree
   - Random Forest
5. Model evaluation using:
   - Accuracy
   - Precision
   - Recall
   - F1-score

---

## Results

### Decision Tree

Accuracy: **0.8717**

However, the classification report revealed an important limitation.  
The model predicted almost all cases as **not readmitted**, which resulted in very poor detection of the minority class (patients who were readmitted).

This shows that **accuracy alone can be misleading when the dataset is imbalanced**.

### Random Forest

The Random Forest model improved the ability to identify **positive cases (readmitted patients)** by combining multiple decision trees. Although the overall accuracy may not differ drastically, the model provides **better detection of readmission risk**, which is more useful for this task.

---

## Conclusion

This project demonstrates the importance of evaluating machine learning models beyond simple accuracy.

While the Decision Tree provided a clear and interpretable structure, it struggled to identify patients who were actually readmitted due to class imbalance.

The Random Forest model performed better in detecting positive cases, making it a more practical choice for predicting hospital readmissions.

---

## How to Run the Project

1. Clone the repository

```bash
git clone https://github.com/zone2233/hospital-readmission-ml.git
cd hospital-readmission-ml
```

2. Install dependencies

```bash
pip install -r requirements.txt
```

3. Open the notebook

```bash
jupyter notebook
```

4. Run the notebook:

```
notebooks/readmission_models.ipynb
```

## Technologies Used

- Python
- Pandas
- Scikit-learn
- Matplotlib
- Jupyter Notebook