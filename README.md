<p align="center">
  <a href="#" target="_blank">
    <img src="assets/logo.png" width="400" alt="Skin Cancer AI Logo">
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.9+-3776AB?logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/TensorFlow-2.15+-FF6F00?logo=tensorflow&logoColor=white">
  <img src="https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white">
  <img src="https://img.shields.io/badge/Google%20Gemini-8E75C2?logo=googlegemini&logoColor=white">
  <img src="https://img.shields.io/badge/HuggingFace-FFD21E?logo=huggingface&logoColor=black">
</p>

<div align="center">

*An advanced AI-driven diagnostic tool for skin lesion analysis and automated medical reporting*

[Key Features](#key-features) • [Repository Structure](#repository-structure) • [Installation](#installation) • [Quick Start](#quick-start) • [Disclaimer](#disclaimer)

</div>

---

## Overview

**SkinCare AI** is a high-performance diagnostic support tool that bridges the gap between Deep Learning and clinical reporting. By leveraging a specialized **VGG16 architecture** and the **Google Gemini API**, the system provides a dual-layer service:

1.  **Computer Vision Analysis**: Instant classification of dermoscopic images to detect malignant or benign lesions.
2.  **Generative AI Reporting**: Automated synthesis of medical-grade reports, translating complex AI outputs into structured, multi-lingual documentation.

Designed for educational and research purposes, this project demonstrates a complete **MLOps pipeline**, from model hosting on HuggingFace to a responsive FastAPI-powered web interface.

---

## Key Features

### Advanced AI Analysis
- **Deep Learning Core**: Utilizes a fine-tuned CNN model (hosted on HuggingFace Hub) optimized for skin lesion feature extraction.
- **Binary Classification**: Precise "Cancerous" vs. "Non-Cancerous" detection using VGG16-based spatial analysis.
- **Image Preprocessing**: Automated resizing and normalization following the ImageNet/VGG standards for maximum accuracy.

### Intelligent Medical Reporting
- **LLM Integration**: Powered by **Google Gemini Pro**, generating detailed clinical insights based on the AI prediction. 
- **Multi-lingual Support**: Seamless report generation in **English 🇺🇸**, **French 🇫🇷**, and **Arabic 🇸🇦** (utilizing `arabic-reshaper` for correct RTL rendering).
- **Expert Narratives**: Reports include potential observations, recommendations, and structured summaries.

### Document Export System
- **PDF Generation**: High-quality PDF export featuring custom fonts (Amiri) for multilingual compatibility.
- **Word (DOCX) Support**: Professional document formatting using `python-docx` for editable medical records.
- **Markdown Processing**: Converts raw AI insights into clean, readable text before document conversion.

### Modern User Experience
- **Responsive UI**: A lightweight, intuitive frontend built with vanilla JS and CSS.
- **Real-time Feedback**: Live analysis status and instant model-loading confirmation from the FastAPI backend.
- **Privacy Focused**: Direct local processing (Backend) with secure API calls to generative services.

---

## Technology Stack

| Category | Technologies |
|----------|--------------|
| **Backend** | ![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi) ![Uvicorn](https://img.shields.io/badge/Uvicorn-499848?style=for-the-badge&logo=python&logoColor=white) |
| **Frontend** | ![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white) ![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white) ![JavaScript](https://img.shields.io/badge/javascript-%23F7DF1E.svg?style=for-the-badge&logo=javascript&logoColor=black) |
| **AI & ML** | ![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white) ![HuggingFace](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Spaces-yellow?style=for-the-badge) ![Google Gemini](https://img.shields.io/badge/Google%20Gemini-8E75C2?style=for-the-badge&logo=googlegemini&logoColor=white) |
| **Libraries** | ![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white) ![Pillow](https://img.shields.io/badge/Pillow-11557c?style=for-the-badge&logo=python&logoColor=white) |
| **Reporting** | ![PDF](https://img.shields.io/badge/FPDF2-red?style=for-the-badge&logo=adobe-acrobat-reader&logoColor=white) ![Word](https://img.shields.io/badge/Python--Docx-blue?style=for-the-badge&logo=microsoft-word&logoColor=white) |

---

## Repository Structure

```text
📦 SkinCare-AI
├── 📂 api/                        # Backend Application (FastAPI)
│   ├── fonts/                  # Custom fonts (Amiri) for multilingual PDF generation
│   └── main.py                 # API server logic & AI model integration
├── 📂 images/                     # Documentation assets
│   ├── demo.gif                # Video GIF demonstration of the app
│   ├── logo.png                # Project branding
│   └── result.png              # Sample analysis output
├── about.html                  # "About Us" page 
├── contact.html                # Contact and support page
├── index.html                  # Main Dashboard (Frontend)
├── requirements.txt            # Project dependencies & versions
├── script.js                   # Frontend logic (API calls & UI interactions)
├── style.css                   # Custom UI styling & layout
└── .gitignore                  # Rules for files to be excluded from Git
```

---

## Installation

### Prerequisites
- **Python:** 3.9 or higher (Tested on 3.12)
- **RAM:** 4GB minimum (8GB recommended for TensorFlow model loading)
- **Disk Space:** ~500MB (Model + Dependencies)
- **Internet:** Required for first-run (Model download from HuggingFace) and Gemini API calls.

### Setup

Follow these steps to set up the project locally:

1. Clone the repository:
```bash
git clone https://github.com/m-belefqih/SkinCare-AI.git
cd SkinCare-AI
```

2. Create virtual environment:
```bash
python3 -m venv venv
```

3. Activate the virtual environment:
```bash
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### Dependencies

The project relies on these **core packages**:
- **FastAPI / Uvicorn**: Backend infrastructure and ASGI server.
- **TensorFlow**: Core engine for VGG16 model inference.
- **Google GenAI**: Interface for Gemini Pro report synthesis.
- **HuggingFace Hub**: Automated model weights retrieval.
- **Arabic-Reshaper / Bidi**: Necessary for RTL (Arabic) PDF rendering.

See `requirements.txt` for complete list.

---

## Quick Start

1. Set up Google Gemini API Key:
  Open `api/main.py` and replace `GEMINI_API_KEY` with your token from [Google AI Studio](https://aistudio.google.com/).

1. Run the Backend Server:
```bash
cd api
uvicorn main:app --reload
```

1. Launch the Frontend:
  Simply open `index.html` in your preferred web browser (Brave/Firefox recommended).

---

## Result

<img src="assets/demo.gif" alt="Sample Output" style="border-radius: 10px; shadow: 5px 5px 15px rgba(0,0,0,0.1);">

### Usage

1. **Language Selection**: Choose between 🇬🇧 English, 🇫🇷 French, or 🇸🇦 Arabic.
2. **Image Upload**: Upload a high-resolution dermoscopic image (JPG/PNG).
3. **AI Inference**: Click **"Analyze Image"** to trigger the VGG16 model.
4. **Report Export**: Review the Gemini-generated analysis and download as **PDF** or **Word**.

---

## Disclaimer

> **IMPORTANT**: This tool is developed for **educational and research purposes only**. The AI-generated analysis is **NOT** a substitute for professional medical diagnosis, prognosis, or treatment. 
> 
> - **Do not** use this tool for clinical decision-making.
> - **Always** consult a qualified dermatologist or healthcare provider for any skin concerns.
> - The authors are not responsible for any misuse of the information provided by this software.

---

**Last Updated**: February 06, 2026
