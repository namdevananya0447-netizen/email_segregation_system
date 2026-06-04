# Shipping Email Segregation & Information Extraction System

## Overview

This project is an NLP and Machine Learning based system that automatically classifies shipping emails into different business categories and extracts important commercial information from them.

The system is designed to process unstructured shipping emails and convert them into structured data that can be used for further analysis and automation.

## Features

### Email Classification

The system classifies shipping emails into the following categories:

- TONNAGE
- CARGO_VC (Voyage Charter Cargo)
- CARGO_TC (Time Charter Cargo)

### Information Extraction

#### TONNAGE Emails

Extracts:

- Vessel Name
- DWT (Deadweight Tonnage)
- Vessel Type
- Open Port
- Open Date

#### CARGO_VC Emails

Extracts:

- Load Port
- Discharge Port
- Laycan
- Cargo Name
- Cargo Type

#### CARGO_TC Emails

Extracts:

- Delivery Port
- Redelivery Port
- Duration
- Laycan

### Named Entity Recognition (NER)

Uses spaCy NLP to identify:

- Company Names
- Dates

### Structured Output

Returns extracted information in JSON format for easy integration with downstream systems.

---

## Technologies Used

- Python
- Scikit-learn
- spaCy
- Pandas
- NumPy
- Regular Expressions (Regex)
- Pickle

---

## Machine Learning Pipeline

### Text Preprocessing

- Text Cleaning
- Tokenization
- TF-IDF Vectorization

### Classification

Support Vector Machine (SVM) classifier is used for email categorization.

### Information Extraction

A combination of:

- Regular Expressions
- Rule-Based Matching
- spaCy Named Entity Recognition

is used to extract relevant fields from emails.

---

## Why SVM?

Support Vector Machine (SVM) was selected because:

- Performs well on small datasets
- Handles high-dimensional TF-IDF features effectively
- Creates clear decision boundaries between classes
- Commonly used for text classification tasks

---

## Project Workflow

```text
Incoming Email
       │
       ▼
TF-IDF Vectorization
       │
       ▼
SVM Classifier
       │
       ▼
Email Category Prediction
       │
       ▼
Information Extraction
       │
       ▼
Structured JSON Output
```

---

## Example Input

```text
MV SHENG AN HAI DWT 56564 OPEN XIAMEN CHINA O/A 2ND JUNE 2026

BULK CARRIER AVAILABLE
PRIME MARITIME INC PIRAEUS
```

### Predicted Category

```text
TONNAGE
```

### Extracted Output

```json
{
  "vessel_name": "MV SHENG AN HAI",
  "dwt": "56564 DWT",
  "open_port": "XIAMEN CHINA",
  "open_date": "2ND JUNE 2026"
}
```

---

## Installation

### Clone Repository

```bash
git clone https://github.com/yourusername/shipping-email-segregation.git
cd shipping-email-segregation
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Download spaCy Model

```bash
python -m spacy download en_core_web_sm
```

---

## Running the Project

### Train the Model

Run the training notebook/script to create the trained classifier.

### Predict on New Emails

```python
category = svm_pipeline.predict([email])[0]
fields = extract_fields(email, category)

print(category)
print(fields)
```

---

## Project Structure

```text
shipping-email-segregation/
│
├── data/
│   └── training_dataset.csv
│
├── notebooks/
│   └── email_api.ipynb
│
├── models/
│   └── shipping_model.pkl
│
├── extractors.py
├── classifier.py
├── predict.py
├── requirements.txt
├── README.md
└── .gitignore
```

---

## Future Improvements

- Web-based user interface
- REST API deployment
- Additional shipping email categories
- Improved NER models
- Deep Learning based classification
- Automated email ingestion from mail servers

---

## Learning Outcomes

Through this project, I gained hands-on experience with:

- Natural Language Processing (NLP)
- Text Classification
- TF-IDF Vectorization
- Support Vector Machines (SVM)
- Information Extraction
- Regular Expressions
- spaCy Named Entity Recognition
- Machine Learning Pipelines
- Structured Data Extraction

---
Ananya Namdev

Machine Learning & NLP Learning Project
