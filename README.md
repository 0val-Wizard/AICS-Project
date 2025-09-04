# AICS-Project
AI for Cybersecurity(AICS) is Year 3 TP Elective Module. It introduces knowledge and skills needed to implement Artificial Intelligence (AI) in cybersecurity. Topics covered in the subject will include an introduction to cybersecurity, implementations of AI in cybersecurity, and defending against threats targeting AI technologies.

## What did I work on in this project?
I worked on;
1. ML Pipeline
2. Report
3. Presentation

## What is happening in my Pipeline?
My pipeline takes raw URLs → cleans → engineers lexical + text features → trains & compares models → selects the best → saves for deployment.
It’s a complete ML lifecycle designed to stop phishing/malicious websites in practice.

## What is the Report discussing?
The report investigates the use of machine learning for malicious URL detection. The aim is to develop a pipeline that can identify phishing, malware, and defacement websites by analyzing URL structures and patterns, ultimately improving cybersecurity defenses.
-------------------

## Detailed Summary of Pipeline
1. Background & Dataset
- Dataset of URLs classified into benign, phishing, malware, and defacement.
- Initial tasks:
  - Load dataset, remove unwanted index columns.
  - Handle missing/broken URLs.
- Create subsets of URLs by category (phishing, malware, defacement, benign).

2. Data Pre-Processing
- Cleaned and standardized the dataset:
  - Removed duplicates, normalized columns.
  - Converted class labels into binary → label = 0 (benign) vs. 1 (malicious).
  - Checked class imbalance with value_counts.

3. Feature Engineering
- Extracted lexical features directly from URLs:
  - url_length, digit_count, special_char_count.
  - Slash count (count_slashes), presence of suspicious keywords (login, free, verify, etc.).
  - Indicators: use of IP address in domain, shortening services, abnormal structures.
- Added categorical/domain-based features:
  - Primary domain, top-level domain (TLD).
- Text-based features:
  - Applied TF-IDF vectorization on URLs to capture patterns.
  - Reduced dimensionality with TruncatedSVD (LSA).

4. Train-Test Split
- Separated features (X) and labels (y).
- Split into train and test sets.
-  Applied StandardScaler for numeric normalization.

5. Model Training
- Implemented supervised ML algorithms (scikit-learn):
  - Logistic Regression
  - Random Forest
  - Gradient Boosting
  - SVM

- Balanced classes with compute_class_weight.
- Evaluated models using:
  - Accuracy, Precision, Recall, F1-Score
  - Confusion Matrix
  - ROC-AUC curves

6. Model Evaluation
- Compared performance across models.
- Random Forest / Gradient Boosting typically performed best for this dataset.
- Highlighted precision vs. recall trade-offs (important for phishing detection where false negatives are risky).

7. Deployment Prep
- Identified best feature set (lexical + TF-IDF).
- Saved preprocessing pipeline and model for reuse.
- Ready for deployment in phishing/malware URL detection systems.

## Detailed Summary of Report
### Dataset & Preprocessing
- Dataset contains URLs labeled as benign, phishing, malware, or defacement.
- Preprocessing steps included:
    - Cleaning & removing duplicates.
    - Standardizing formats.
    - Converting to a binary classification task: benign (0) vs. malicious (1).
    - Checking for class imbalance.

### Feature Engineering
- Lexical features: length of URL, number of digits, special characters, slashes.
- Keyword-based indicators: presence of suspicious terms like login, free, verify.
- Domain-level features: extracted domains and top-level domains.
- Text features:
    - Applied TF-IDF vectorization to URLs.
    - Reduced dimensionality with TruncatedSVD (LSA).

### Model Training & Evaluation
- Models used: Logistic Regression, Random Forest, Gradient Boosting, SVM.
- Balanced training using class weights.
- Evaluation metrics: Accuracy, Precision, Recall, F1-score, ROC-AUC, and Confusion Matrix.
- Best performers: Random Forest and Gradient Boosting — strong precision & recall, effective at minimizing false negatives.

### Findings & Conclusion
- The pipeline successfully processes raw URLs into meaningful features for classification.
- Tree-based models delivered the best results, offering robustness in detecting malicious patterns.
- The project demonstrates a complete ML lifecycle: data cleaning → feature extraction → model training → evaluation → deployment readiness.

### In essence:
Your report shows how machine learning can be applied to cybersecurity, specifically detecting malicious URLs with high accuracy using a carefully engineered pipeline and strong classifiers.
