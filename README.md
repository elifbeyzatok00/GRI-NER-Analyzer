# Project README

This project includes two different model versions for processing and analyzing data from PDF documents and JSON files. This README file provides an overview of the features, technologies, and steps for both models.

## Table of Contents

1. [Model Versions](#model-versions)
2. [Model Version 1](#model-version-1)
3. [Model Version 2](#model-version-2)
4. [General Technologies and Tools](#general-technologies-and-tools)

## Model Versions

This project includes two different model versions:

- **model_version_1:** Focuses on identifying, classifying tables in PDF documents, and extracting GRI standards and page references.
- **model_version_2:** Involves creating and evaluating a Named Entity Recognition (NER) model using report texts from JSON files.

## Model Version 1

This model focuses on identifying, classifying tables in PDF documents, and extracting specific information. The technologies used and steps are as follows:

### 1. Finding PDF Tables

**Technologies Used:**

- **Python**
- **Tabula-py:** A Python library used for extracting tables from PDF files.
- **Pandas:** A powerful Python library for data processing and analysis.

**Steps:**

- PDF tables from all pages are read using `tabula.read_pdf` and stored in a `tables` list.
- These tables are processed in a loop and printed.

### 2. Classifying GRI Tables

**Technologies Used:**

- **Python**
- **Scikit-learn:** A popular Python library for machine learning. A Naive Bayes classifier is used here.
- **Pandas:** Used to process data and create a training dataset for the model.

**Steps:**

- Extracted tables from PDFs are compared with pre-labeled tables used as training data.
- Tables' texts are converted into feature vectors using `CountVectorizer`.
- A Naive Bayes model is trained on these features and then classifies whether the tables are GRI tables.

### 3. Extracting GRI Standards and Page References from GRI Tables

**Technologies Used:**

- **Python**
- **SpaCy:** A powerful Python library for natural language processing. A Named Entity Recognition (NER) model is trained and used here.

**Steps:**

- SpaCy's NER model is used to extract specific GRI standards and page references from the text in GRI tables.
- The model is applied to the extracted rows from GRI tables to label entities (e.g., `gri_standard`, `page_reference`).

### 4. Evaluating Naive Bayes and NER Models

**Technologies Used:**

- **Python**
- **Scikit-learn:** Used for evaluating model performance with classification reports, confusion matrices, and accuracy scores.
- **Matplotlib and Seaborn:** Used for visualizing the confusion matrix.

**Steps:**

- The performance of the Naive Bayes model is evaluated on test data, reporting accuracy, and confusion matrix.
- The NER model's accuracy is evaluated on sample texts and results are presented as scores.

## Model Version 2

This model involves creating and evaluating an NER model using NLP techniques on report texts from JSON files. The project steps and technologies used are summarized below:

### 1. Extracting Data from JSON and Converting to Text Files

- **Objective:** Extract `Report_ID` and `PDF` content from the JSON file and save each report as a text file named `Report_ID.txt`.
- **Technologies:** Python, JSON, Regex, File I/O
- **Description:** The JSON file is read, and the PDF content of each report is cleaned and stripped of Unicode characters. The cleaned content is then saved to the corresponding `Report_ID.txt` file.

### 2. Creating Dataset for NER Model from JSON Files

- **Objective:** Create training and evaluation datasets for the NER model using labeled data in JSON format.
- **Technologies:** Python, SpaCy, JSON
- **Description:** Data labeling is performed using the [NER Annotation Tool](https://tecoholic.github.io/ner-annotator/). This tool allows for labeling entities (e.g., GRI standards, page references) in the text. (NER Annotation Tool GitHub repository: [ner-annotator GitHub](https://github.com/tecoholic/ner-annotator)) Labeled JSON files are used to extract and clean text and entity information, which is then used to create datasets. This dataset is divided into `TRAIN_DATA` and `EVAL_DATA` for model training and evaluation.

### 3. Creating and Training the NER Model

- **Objective:** Create and train a custom NER model using SpaCy.
- **Technologies:** SpaCy, Python
- **Description:** A model is created using SpaCy’s NER pipeline. The model is trained for 100 iterations with the training data and saved.

### 4. Testing and Evaluating the Model

- **Objective:** Test the trained NER model and evaluate its performance.
- **Technologies:** SpaCy, Python, Matplotlib, Seaborn, Pandas
- **Description:** The model is tested on evaluation data, and results are assessed using metrics like Precision, Recall, and F1-Score. Results are visualized with graphs.

### 5. Processing Unlabeled Text Files with the NER Model

- **Objective:** Process unlabeled report files with the trained NER model to extract key information such as `page_references`, `direct_answers`, and `gri_standards`.
- **Technologies:** Python, SpaCy
- **Description:** Each report file is processed by the model to extract relevant entities, which can then be analyzed using the extracted data.

## General Technologies and Tools

- **Python:** The primary programming language used for all data processing, machine learning, and natural language processing steps.
- **Tabula-py, Scikit-learn, SpaCy:** Key Python libraries used for PDF table extraction, machine learning classification, and natural language processing.
- **JSON:** The data format used to store reports.
- **Matplotlib and Seaborn:** Libraries used for visualizing model performance.
- **Google Colab:** Used for running, testing, and training models.

Both models aim to automate specific data processing and analysis steps, making the processes more efficient. Relevant libraries and tools have been used to test the performance of both models.
