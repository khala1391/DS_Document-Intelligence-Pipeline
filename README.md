# Document Intelligence Pipeline

An automated document analysis app for Thai business documents — extracts text, identifies entities, classifies document type, and summarizes key information.

**Live Demo:** [doc-intelligence.streamlit.app](https://datascienceportfolio-bfssupkanpzfwcsh4inie3.streamlit.app)

---

## Features

| Stage | Description |
| --- | --- |
| **OCR** | Extracts text from PDF and images (PNG, JPG) using EasyOCR — supports both text-based and scanned documents |
| **NER** | Identifies named entities: dates, amounts, organizations, persons, addresses, tax IDs, invoice numbers |
| **Classification** | Classifies document type (invoice, contract, report, etc.) with confidence score via Gemini AI |
| **Summarization** | Extracts key parties, important dates, monetary values, and a plain-language summary |

---

## Tech Stack

- **Frontend:** Streamlit
- **OCR:** EasyOCR
- **NLP/NER:** PyThaiNLP
- **AI (Classification & Summarization):** Google Gemini 2.5 Flash
- **PDF Processing:** PyMuPDF

---

## Getting Started

### Prerequisites

- Python 3.11+
- Google Gemini API Key — get one free at [aistudio.google.com](https://aistudio.google.com)

### Installation

```bash
git clone https://github.com/khala1391/DS_Document-Intelligence-Pipeline.git
cd DS_Document-Intelligence-Pipeline
python -m venv .venv
.venv\Scripts\activate        # Windows
pip install -r requirements.txt
```

### Run

```bash
streamlit run app.py
```

Open `http://localhost:8501`, enter your Gemini API Key in the sidebar, upload a document, and click **ประมวลผล**.

---

## Usage

1. **Enter API Key** — paste your Google Gemini API Key in the sidebar
2. **Upload a document** — PDF, PNG, or JPG (first page only)
3. **Click ประมวลผล** — the pipeline runs OCR → NER → Classification → Summary
4. **View results** across 4 tabs: OCR / NER / Classification / Summary
5. **Download** results as JSON or TXT from the top bar

No document? Use the **ดูตัวอย่างผลลัพธ์** button to preview sample outputs for an invoice, employment contract, or operations report.

---

## Project Structure

```text
doc_intelligence/
├── app.py                  # Main Streamlit app
├── requirements.txt
├── pipeline/
│   ├── ocr.py              # EasyOCR wrapper
│   ├── ner.py              # Named entity recognition
│   ├── classifier.py       # Document classification via Gemini
│   └── summarizer.py       # Document summarization via Gemini
└── utils/
    ├── display.py          # Entity highlighting & rendering
    └── pdf_utils.py        # PDF text extraction & conversion
```

---

## Author

Yuttapong M. — [linkedin.com/in/yuttapong-m](https://www.linkedin.com/in/yuttapong-m/)
