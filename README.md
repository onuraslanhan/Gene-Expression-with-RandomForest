Gene Expression Classification with Random Forest (ALL vs AML)

A machine learning project that classifies leukemia patients into two subtypes — ALL (Acute Lymphoblastic Leukemia) and AML (Acute Myeloid Leukemia) — based on gene expression data, using a Random Forest classifier.

Dataset

The dataset comes from the classic Golub et al. leukemia gene expression study, containing gene expression measurements (~7,000 genes) for 38 patients, each labeled as ALL or AML.

Tech Stack
Python
Pandas
Scikit-Learn (RandomForestClassifier, train_test_split)
Process
Data Loading: Loaded the gene expression matrix and the patient label file separately.
Data Cleaning: Removed redundant "call" columns and non-numeric metadata columns from the gene expression matrix.
Reshaping: Transposed the data so that each row represents a patient and each column represents a gene (the raw format had genes as rows).
Merging: Joined the gene expression data with patient cancer-type labels on patient ID.
Encoding: Converted the categorical target (ALL/AML) into a numeric column.
Train/Test Split: Split the 38 patients into training and test sets.
Modeling: Trained a Random Forest classifier and evaluated it on the held-out test set.
Result
Test accuracy: ~87.5%
Train accuracy: 100%
Limitations / What I Learned

This dataset has far more features (~7,000 genes) than samples (38 patients), which makes the model prone to overfitting — it can effectively "memorize" the training patients rather than learning a generalizable pattern. I confirmed this by comparing train and test scores directly, and reduced it somewhat using max_depth and min_samples_leaf to constrain the trees. Given the small test set (~8 patients), the accuracy score itself should be interpreted cautiously rather than treated as a precise, stable measure of performance.

This project was a hands-on introduction to working with high-dimensional biological data, and to critically evaluating a model's output rather than accepting a high score at face value.
