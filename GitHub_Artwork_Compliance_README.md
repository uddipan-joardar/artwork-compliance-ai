# 🔍 Artwork Compliance Intelligence Platform

> **Agentic AI system automating product artwork compliance verification across 14 global markets**  
> GPT-4o Vision · LangChain Tool-Calling Agents · Pytesseract OCR · Streamlit · Power BI · Power Automate

---

## 🎯 Business Problem

Global FMCG companies must verify that product artwork (labels, packaging) meets nutritional labeling regulations across 14+ markets. This was done **100% manually** — compliance teams comparing artwork images against Excel truth tables line by line, consuming thousands of hours per year.

## ✅ Solution

An end-to-end **Agentic AI compliance platform** that:
1. Accepts product artwork images and Excel nutritional truth tables as input
2. Autonomously extracts text using GPT-4o Vision + OCR
3. Parses and cross-references nutritional data
4. Flags labeling violations with structured LLM reasoning
5. Generates downloadable audit reports
6. Feeds results into a real-time Power BI executive dashboard

## 📊 Impact

| Metric | Result |
|---|---|
| Manual verification effort | **70% reduction** |
| Markets covered | **14 global markets** |
| Adoption | Standard global compliance workflow |
| Stakeholder visibility | Near-real-time Power BI dashboard |

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    USER (Compliance Team)                    │
│              Uploads artwork image + Excel file             │
└─────────────────────┬───────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────────────┐
│                  STREAMLIT UI (Frontend)                     │
│         Upload · Validate · Download Audit Report           │
└─────────────────────┬───────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────────────┐
│              LANGCHAIN TOOL-CALLING AGENT                    │
│                                                             │
│  Tool 1: GPT-4o Vision → extract text from artwork image    │
│  Tool 2: Pytesseract OCR → fallback text extraction         │
│  Tool 3: Excel Parser → parse nutritional truth table       │
│  Tool 4: Compliance Checker → flag violations via LLM       │
│  Tool 5: Report Generator → structured audit output         │
└─────────────────────┬───────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────────────┐
│              POWER BI EXECUTIVE DASHBOARD                    │
│   Compliance KPIs · Market breakdown · Violation trends     │
│         Auto-refreshed via Power Automate pipeline          │
└─────────────────────────────────────────────────────────────┘
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| LLM | GPT-4o (Azure OpenAI) |
| Agent Framework | LangChain Tool-Calling Agents |
| Vision / OCR | GPT-4o Vision, Pytesseract, OpenCV |
| Data Parsing | Python, Pandas, openpyxl |
| Frontend | Streamlit |
| BI Dashboard | Power BI (Advanced), Power Automate |
| Cloud | Azure OpenAI, Azure Web App |
| Language | Python 3.10+ |

---

## 📁 Repository Structure

```
artwork-compliance-ai/
├── agents/
│   ├── compliance_agent.py        # LangChain tool-calling agent
│   ├── tools/
│   │   ├── vision_extractor.py    # GPT-4o Vision text extraction
│   │   ├── ocr_extractor.py       # Pytesseract OCR fallback
│   │   ├── excel_parser.py        # Nutritional truth table parser
│   │   ├── compliance_checker.py  # LLM violation flagging
│   │   └── report_generator.py    # Structured audit report
├── app/
│   └── streamlit_app.py           # Self-service UI
├── prompts/
│   └── compliance_prompt.py       # Prompt templates
├── utils/
│   ├── image_utils.py
│   └── excel_utils.py
├── tests/
│   └── test_compliance_agent.py
├── requirements.txt
└── README.md
```

---

## 🚀 Key Engineering Decisions

**Why LangChain Tool-Calling over a simple LLM call?**
Labeling compliance requires sequential, deterministic steps — extract, parse, compare, flag. A tool-calling agent enforces this structure, handles retries on tool failures, and produces auditable reasoning traces.

**Why GPT-4o Vision + OCR fallback?**
Artwork images vary widely in quality and format. GPT-4o Vision handles structured label layouts natively; Pytesseract provides a fallback for low-resolution or print-format images.

**Why Streamlit for the UI?**
Compliance teams are non-technical. Streamlit enabled a no-code self-service interface deployable in days — eliminating daily engineering dependency entirely.

---

## 📬 Contact

**Uddipan Joardar** — [LinkedIn](https://linkedin.com/in/uddipan-joardar38302580) · [Email](mailto:dip.joardar@gmail.com)
