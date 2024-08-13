This project involves extracting report texts from a JSON file, creating and evaluating a Named Entity Recognition (NER) model using Natural Language Processing (NLP) techniques. The project steps and technologies used are summarized below:

### 1. Extracting Data from JSON File and Converting to Text Files

- **Objective:** Extract `Report_ID` and `PDF` content from the JSON file and save each report as a text file named `Report_ID.txt`.
- **Technologies:** Python, JSON, Regex, File I/O
- **Description:** The JSON file is read, and the content of each report is cleaned and stripped of Unicode characters. The cleaned content of each report is then saved to the corresponding `Report_ID.txt` file.

### 2. Creating a Dataset for the NER Model from JSON Files

- **Objective:** Create training and evaluation datasets for the NER model using labeled data in JSON format.
- **Technologies:** Python, SpaCy, JSON
- **Description:** Data labeling is performed using the [NER Annotation Tool](https://tecoholic.github.io/ner-annotator/). This tool allows for labeling entities (e.g., GRI standards, page references) in the text. (The NER Annotation Tool GitHub repository: [ner-annotator GitHub](https://github.com/tecoholic/ner-annotator)) Labeled JSON files are used to extract and clean text and entity information, which is then used to create datasets. This dataset is divided into `TRAIN_DATA` and `EVAL_DATA` for model training and evaluation.

### 3. Creating and Training the NER Model

- **Objective:** Create and train a custom NER model using SpaCy.
- **Technologies:** SpaCy, Python
- **Description:** A model is created using SpaCy’s NER pipeline. The model is trained for 100 iterations with the training data and saved.

### 4. Testing and Evaluating the Model

- **Objective:** Test the trained NER model and evaluate its performance.
- **Technologies:** SpaCy, Python, Matplotlib, Seaborn, Pandas
- **Description:** The model is tested on the evaluation data, and results are assessed using metrics like Precision, Recall, and F1-Score. Results are visualized with graphs.

### 5. Processing Unlabeled Text Files with the NER Model

- **Objective:** Process unlabeled report files with the trained NER model to extract key information such as `page_references`, `direct_answers`, and `gri_standards`.
- **Technologies:** Python, SpaCy
- **Description:** Each report file is processed by the model to extract relevant entities, which can then be analyzed using the extracted data.

### Technologies Used:

- **Python:** The primary programming language used for all project steps.
- **SpaCy:** The Python library used for NLP tasks and training the NER model.
- **JSON:** The data format used to store the reports.
- **Matplotlib and Seaborn:** Libraries used for visualizing model performance.
- **Pandas:** A data analysis library used for organizing and inspecting data.
