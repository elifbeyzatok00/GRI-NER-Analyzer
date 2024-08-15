This project focuses on identifying, classifying, and extracting specific information from tables in PDF documents. The technologies used and the details of the steps are as follows:

### 1. Finding PDF Tables

**Technologies Used:**

- **Python**
- **Tabula-py**: A Python library used for extracting tables from PDF files.
- **Pandas**: A powerful Python library for data processing and analysis.

**Steps:**

- The `tabula.read_pdf` function is used to read tables from all pages of the PDF file and save them into the `tables` list.
- These tables are processed in a loop for each table and printed to the screen.

### 2. Classifying GRI Tables

**Technologies Used:**

- **Python**
- **Scikit-learn**: A popular Python library for machine learning. A Naive Bayes classifier is used here.
- **Pandas**: Used for processing data and creating a training dataset for the model.

**Steps:**

- Tables extracted from the PDF are compared with previously labeled tables used as training data.
- `CountVectorizer` is used to convert the text of the tables into feature vectors.
- The Naive Bayes model is trained on these features and then classifies whether the tables are GRI tables or not.

### 3. Extracting GRI Standards and Page References from GRI Tables

**Technologies Used:**

- **Python**
- **SpaCy**: A powerful Python library for natural language processing. A Named Entity Recognition (NER) model has been trained and used here.

**Steps:**

- SpaCy's NER model is used to extract specific GRI standards and page references from the text in GRI tables.
- The model is applied to the rows extracted from GRI tables, and labels for each row are determined (e.g., `gri_standard`, `page_reference`).

### 4. Evaluating Naive Bayes and NER Models

**Technologies Used:**

- **Python**
- **Scikit-learn**: Classification reports, confusion matrices, and accuracy scores are calculated for model evaluation.
- **Matplotlib and Seaborn**: Used for visualizing the confusion matrix.

**Steps:**

- The performance of the Naive Bayes model is evaluated on test data, and accuracy, confusion matrix, and reports are provided.
- The accuracy of the NER model is evaluated on sample texts, and the results are presented as scores.

### General Technologies and Tools

- **Python**: Used for all data processing, machine learning, and natural language processing steps.
- **Google Colab**: Used for running, testing, and training the code and models.
- **Tabula-py, Scikit-learn, SpaCy**: Fundamental Python libraries used for PDF table extraction, machine learning classification, and natural language processing.

These steps cover the process of automatically extracting GRI standards and related page references from PDF documents. The Naive Bayes classifier and SpaCy’s NER model are core components of this process.