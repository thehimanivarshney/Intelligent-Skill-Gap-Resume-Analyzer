# 🧠 Intelligent Skill-Gap & Resume Analyzer using Transformer-Based Deep Learning

> An AI-powered resume analysis system that leverages Transformer-based Deep Learning and Natural Language Processing (NLP) to compare resumes with job descriptions, identify skill gaps, calculate ATS compatibility, evaluate communication quality, and recommend personalized learning paths.

---

# 📌 Table of Contents

- Project Overview
- Objectives
- Key Features
- System Architecture
- Technologies Used
- Deep Learning Concepts
- Dataset Information
- Installation
- Project Workflow
- Methodology
- Results & Visualizations
- Project Structure
- Usage
- Sample Output
- Future Enhancements
- Limitations
- Conclusion
- Author

---

# 📖 Project Overview

Recruiters receive hundreds of resumes for every job opening. Traditional Applicant Tracking Systems (ATS) primarily rely on keyword matching, which often fails to understand the actual semantic meaning of a candidate's experience.

The **Intelligent Skill-Gap & Resume Analyzer** addresses this limitation by using **Sentence-BERT (SBERT)**, a Transformer-based Deep Learning model, to perform semantic comparison between resumes and job descriptions instead of simple keyword matching.

The system also provides:

- Resume–Job semantic similarity score
- Skill gap analysis
- Communication quality evaluation
- ATS compatibility score
- Bias-blind resume anonymization
- Personalized learning recommendations

---

# 🎯 Objectives

The primary objectives of this project are:

- Compare resumes with job descriptions using Transformer embeddings.
- Identify missing technical skills required for a target role.
- Calculate semantic similarity between resumes and job descriptions.
- Improve resume quality through communication analysis.
- Remove Personally Identifiable Information (PII) for bias-blind screening.
- Generate ATS compatibility scores.
- Recommend learning resources based on missing skills.

---

# ✨ Key Features

## 1. Transformer-Based Semantic Matching

Uses the **Sentence-BERT (all-MiniLM-L6-v2)** model to generate contextual embeddings for resumes and job descriptions.

Instead of matching exact keywords, the system understands semantic meaning.

Example:

Resume:

> Developed REST APIs using Flask.

Job Description:

> Experience in Python backend development.

Traditional keyword matching:

❌ Low match

Sentence-BERT:

✅ High semantic similarity

---

## 2. Intelligent Skill Gap Analysis

The system extracts technical skills from both the resume and job description and identifies:

- Resume Skills
- Required Job Skills
- Matched Skills
- Missing Skills

Example:

Matched Skills

- Python
- SQL
- Pandas

Missing Skills

- Docker
- AWS
- Kubernetes

---

## 3. Communication Impact Grader

Evaluates the quality of resume writing using heuristic analysis based on:

- Strong action verbs
- Quantified achievements
- Resume length
- Structural sections

Outputs:

- Communication Score
- Suggestions for improvement

Example Suggestions:

- Add quantified achievements.
- Use stronger action verbs.
- Include more project details.

---

## 4. Bias-Blind Resume Anonymizer

Uses **spaCy Named Entity Recognition (NER)** to detect and anonymize sensitive information including:

- Person Names
- Organizations
- Locations
- Dates
- Emails
- Phone Numbers

Example:

Original:

```
Himani Varshney
Email: abc@gmail.com
```

Anonymized:

```
[PERSON]
Email: [EMAIL]
```

---

## 5. ATS Compatibility Score

Generates a composite ATS score by combining:

- Semantic Similarity
- Communication Score
- Skill Match Percentage

Formula:

```
ATS Score =
0.40 × Semantic Similarity +
0.30 × Communication Score +
0.30 × Skill Match Score
```

---

## 6. Personalized Learning Recommendation Engine

Maps missing skills to recommended learning paths.

Example:

Missing Skill:

Docker

Recommendation:

Learn Docker Fundamentals

---

## 7. Interactive Gradio Interface

Provides a simple interface for analyzing resumes directly from the notebook.

---

# 🏗️ System Architecture

```
                     Resume Dataset
                           │
                           │
                   Text Preprocessing
                           │
                           ▼
               Sentence-BERT (MiniLM)
                           │
                           ▼
                Resume Embeddings
                           │
                           │
Job Description Dataset ───┘
                           │
                           ▼
                 Semantic Similarity
                           │
          ┌────────────────┼────────────────┐
          │                │                │
          ▼                ▼                ▼
   Skill Gap         Communication     ATS Score
    Analysis            Grader
          │                │
          └──────────┬─────┘
                     ▼
         Recommendation Engine
                     │
                     ▼
             Final AI Report
```

---

# 💻 Technologies Used

## Programming Language

- Python

## Deep Learning

- Sentence-BERT
- Transformers
- Hugging Face

## NLP

- spaCy
- NLTK

## Machine Learning

- Scikit-Learn

## Data Processing

- Pandas
- NumPy

## Visualization

- Matplotlib

## User Interface

- Gradio

---

# 🧠 Deep Learning Concepts Used

This project applies the following Deep Learning concepts:

- Transformer Architecture
- Sentence-BERT (SBERT)
- Transfer Learning
- Contextual Word Embeddings
- Dense Vector Representations
- Semantic Similarity
- Cosine Similarity

The pretrained **all-MiniLM-L6-v2** model from Sentence Transformers is used to encode resumes and job descriptions into 384-dimensional embedding vectors.

---

# 📂 Dataset Information

Two datasets were used.

## Resume Dataset

Columns:

- ID
- Resume_str
- Resume_html
- Category

Used Columns:

- Resume_str
- Category

---

## Job Description Dataset

Columns:

- Job Title
- Description

Used Columns:

- Job Title
- Description

---

# ⚙️ Installation

Install required libraries.

```bash
pip install sentence-transformers
pip install transformers
pip install spacy
pip install gradio
pip install pdfplumber
pip install python-docx
pip install PyMuPDF
pip install nltk
```

Download spaCy model.

```bash
python -m spacy download en_core_web_sm
```

Download NLTK resources.

```python
import nltk

nltk.download("stopwords")
nltk.download("wordnet")
```

---

# 🔄 Project Workflow

```
Load Datasets
      │
      ▼
Text Cleaning
      │
      ▼
Generate Sentence Embeddings
      │
      ▼
Semantic Similarity
      │
      ▼
Skill Extraction
      │
      ▼
Skill Gap Analysis
      │
      ▼
Communication Analysis
      │
      ▼
Bias-Blind Resume
      │
      ▼
ATS Score
      │
      ▼
Learning Recommendations
      │
      ▼
Final AI Report
```

---

# 🔬 Methodology

## Step 1

Load Resume Dataset

↓

Load Job Description Dataset

---

## Step 2

Clean text using:

- Lowercasing
- Stop-word removal
- Lemmatization
- Punctuation removal

---

## Step 3

Generate sentence embeddings using

Sentence-BERT

Model:

```
all-MiniLM-L6-v2
```

---

## Step 4

Calculate semantic similarity using

Cosine Similarity

---

## Step 5

Extract technical skills

---

## Step 6

Identify

- Matched Skills
- Missing Skills

---

## Step 7

Calculate

- Communication Score
- ATS Score

---

## Step 8

Generate personalized recommendations

---

# 📊 Results & Visualizations

The notebook generates:

- Top 5 Matching Jobs
- Semantic Similarity Score
- Communication Score
- ATS Score
- Missing Skills Visualization
- Final Resume Dashboard

---

# 📁 Project Structure

```
Intelligent-Skill-Gap-Resume-Analyzer/

│
├── Intelligent_Skill_Gap_Resume_Analyzer.ipynb
├── Resume.csv
├── data.csv
├── resume_analysis_report.json
├── README.md
└── requirements.txt
```

---

# ▶️ Usage

1. Upload the datasets.
2. Run all notebook cells sequentially.
3. Generate embeddings.
4. Analyze resume.
5. View generated report.
6. Launch the Gradio interface.
7. Download the JSON report.

---

# 📈 Evaluation Metrics

The project evaluates resumes using:

- Semantic Similarity Score
- Communication Score
- ATS Compatibility Score
- Number of Matched Skills
- Number of Missing Skills
- Resume Category Prediction (through best semantic match)

---

# 📋 Sample Output

```
==========================================

INTELLIGENT SKILL GAP REPORT

==========================================

Resume Category:
Data Science

Best Matching Job:
Machine Learning Engineer

Semantic Similarity:
89.45%

Communication Score:
82%

ATS Score:
87%

Matched Skills:
Python
SQL
Pandas

Missing Skills:
Docker
AWS
Git

Learning Recommendations:
Learn Docker Fundamentals
AWS Cloud Practitioner
Git & GitHub

==========================================
```

---

# 🚀 Future Enhancements

- PDF resume upload support
- DOCX resume support
- Live GitHub profile validation
- LinkedIn profile integration
- Fine-tuned Transformer models
- Resume rewriting using LLMs
- Real-time job recommendation
- Cloud deployment
- Multi-language support

---

# ⚠️ Limitations

- Skill extraction currently relies on a predefined technical skill dictionary.
- Communication grading is heuristic-based and not powered by a dedicated deep learning model.
- ATS score is an estimated composite score and does not replicate proprietary ATS algorithms.
- The quality of semantic matching depends on the diversity of the job description dataset.

---

# 🎓 Conclusion

The Intelligent Skill-Gap & Resume Analyzer demonstrates how Transformer-based Deep Learning can enhance resume screening beyond traditional keyword matching. By combining semantic embeddings with NLP techniques and analytical modules, the system provides meaningful insights into resume quality, skill gaps, and job compatibility.

The project showcases the practical application of Sentence-BERT, Natural Language Processing, and AI-driven recommendation systems in modern Human Resource (HR) technology.

---

# 👩‍💻 Author

**Himani Varshney**

Bachelor of Computer Applications (BCA)

Dr. A.P.J. Abdul Kalam Technical University (AKTU)

GitHub: https://github.com/thehimanivarshney

---

## ⭐ If you found this project useful, consider giving it a star on GitHub.