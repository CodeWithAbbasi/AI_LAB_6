# Project 2: Information Extraction & Named Entity Recognition (Week 7)

This project focuses on transforming unstructured text from documents like invoices and receipts into structured, queryable data. By building a complete extraction pipeline, the system integrates OCR (Optical Character Recognition), regular expressions (regex), and AI-powered Named Entity Recognition (NER).

---

## 🎯 Project Goals

* 
**Pattern Matching**: Extract specific identifiers such as dates, currency amounts, and invoice/order numbers using regex.


* 
**Named Entity Recognition**: Utilize spaCy to identify people, organizations, and locations within documents.


* 
**Data Visualization**: Use displaCy to create color-coded visualizations of extracted entities.


* 
**Pipeline Integration**: Combine OCR, text preprocessing, and extraction into a unified system that outputs structured JSON data.



---

## 🛠️ Setup Requirements

### 1. Library Installation

To run the extraction pipeline, you must install **spaCy** and the **pytesseract** OCR engine.

```bash
pip install spacy pytesseract

```

### 2. Language Model Download

Download the small English model for spaCy. For higher accuracy, `en_core_web_md` or `en_core_web_lg` can be used.

```bash
python -m spacy download en_core_web_sm

```

---

## 📂 Pipeline Components

### Part 1: Regular Expression Extraction

The system uses custom regex patterns to handle various document formats:

* 
**Dates**: Supports MM/DD/YYYY, DD-MM-YYYY, and ISO formats.


* 
**Currency**: Handles symbols and commas (e.g., $1,250.50) and converts them to float values for processing.


* 
**Identifiers**: Extracts specific patterns like `INV-2024-001` or `ORDER-ABC123`.



### Part 2: Named Entity Recognition (NER)

Using spaCy’s pre-trained models, the pipeline categorizes text into specific entity types:

* 
**PERSON**: Identifies names of individuals.


* 
**ORG**: Identifies companies and organizations.


* 
**GPE/LOC**: Identifies geographical locations and cities.


* 
**MONEY/DATE**: Complements regex extraction for better coverage.



### Part 3: Automated Invoice Processor

The final `process_invoice` function automates the following steps:

1. 
**OCR**: Converts an image (e.g., `sample_invoice.jpg`) into raw text.


2. 
**Regex Extraction**: Pulls structured IDs and financial figures.


3. 
**NER Processing**: Extracts entities from the OCR text.


4. 
**Post-processing**: Identifies the "Total Amount" by finding the maximum value in the extracted amounts.



---

## 📄 Deliverables

* 
**week7_information_extraction.ipynb**: The main development notebook.


* 
**extracted_data.json**: The final structured output of the document processing.


* 
**entities.html**: A visual representation of the NER results created via displaCy.



---

