<!-- Banner -->
![Auto Publishing Agent Banner](assets/banner.png)

<!-- Logo centered -->
<p align="center">
  <img src="assets/logo.png" alt="Auto Publishing Agent Logo" width="120"/>
</p>

<h1 align="center">Auto Publishing Agent</h1>
<h3 align="center">Standardized Promotion · Amplify Differentiated Value</h3>

---

# Table of Contents
- [Purpose & Philosophy](#purpose--philosophy)
- [Features](#features)
  - [Main Image Quality Check](#main-image-quality-check-qa-engine)
  - [Multi-Platform Image Adaptation](#multi-platform-image-adaptation-preset-system)
  - [AI Copywriting Pipeline](#ai-copywriting-pipeline-structured-output)
- [Workflow Architecture](#workflow-architecture)
- [Screenshots](#screenshots)
  - [Main Workflow](#main-workflow)
  - [ImageEdit Subworkflow](#imageedit-subworkflow)
  - [TextEdit Subworkflow](#textedit-subworkflow)
- [Repository Structure](#repository-structure)
- [Requirements](#requirements)
- [Installation & Usage](#installation--usage)
- [Roadmap](#roadmap)
- [License](#license)
- [Contact](#contact)

---

# 🌍 Purpose & Philosophy

A modular, extensible **Auto Publishing Agent** built with n8n.

The goal is to automate the *mechanical and repetitive* parts of publishing—image preparation, platform adaptation, metadata generation, and AI copywriting—so creators and teams can focus on what truly matters:

## **Building differentiated products and delivering differentiated services.**

True value comes from **unique products**, not from struggling with:

- Platform-specific aspect ratio rules  
- Repetitive image resizing  
- Inconsistent copywriting  
- Manual multi-platform posting  

**Promotion should be standardized and automated.  
Differentiation should come from creation, not formatting.**

---

# 🚀 Features

## ✔ Main Image Quality Check (QA Engine)

Evaluates uploaded images according to platform-recommended standards:

- Width / height / ratio detection  
- Portrait orientation verification  
- 4:5 tolerance (±0.04)  
- Minimum short-edge constraints  
- Classification: `high`, `ok`, `low`, `none`  
- Human-readable explanation of failures  

**Workflow:**  
[`P001_AutomaticallyPublishWorks.json`](P001_AutomaticallyPublishWorks.json)

---

## ✔ Multi-Platform Image Adaptation (Preset System)

Automatically generates platform-ready image variants.

Supported presets:

- **Instagram:** 1:1 / 4:5 / 9:16  
- **Facebook:** 1:1 / 4:5 / 9:16 / 16:9  
- **X/Twitter:** 1:1 / 16:9  

Features:

- Smart center cropping  
- Boundary protection  
- Resolution normalization  
- Structured file naming  
- Google Drive upload  

**Workflow:**  
[`P001_sub_ImageEdit.json`](P001_sub_ImageEdit.json)

---

## ✔ AI Copywriting Pipeline (Structured Output)

Generates clear, structured promotional text from a single raw prompt.

Outputs include:

- Platform  
- Title  
- Keywords  
- Content  

Capabilities:

- Supports **OpenAI**, **Gemini**, **OpenRouter**  
- Multi-language (EN + ZH)  
- Prompt routing & round-robin model selection  
- Strict JSON schema validation  

**Workflow:**  
[`P001_sub_TextEdit.json`](P001_sub_TextEdit.json)

---

# 🧠 Workflow Architecture

```
Main Workflow
│
├── Image Quality Check
├── Batch Routing
│
├── ImageEdit Subworkflow  → Multi-platform image generation
└── TextEdit Subworkflow   → AI copy creation
```

---

# 📸 Screenshots

### Main Workflow
![Main Workflow](assets/P001_AutomaticallyPublishWorks.png)

---

### ImageEdit Subworkflow
![ImageEdit Subworkflow](assets/sub_imageEdit.png)

---

### TextEdit Subworkflow
![TextEdit Subworkflow](assets/sub_textEdit.png)

---

# 📦 Repository Structure

```
.
├── README.md
├── P001_AutomaticallyPublishWorks.json
├── P001_sub_ImageEdit.json
├── P001_sub_TextEdit.json
└── assets/
    ├── P001_AutomaticallyPublishWorks.png
    ├── sub_imageEdit.png
    └── sub_textEdit.png
```

---

# 🛠 Requirements

- **n8n** (self-hosted or cloud)
- **Google Drive OAuth2**
- At least one LLM provider:
  - OpenAI
  - Gemini
  - OpenRouter

---

# 📥 Installation & Usage

### 1. Import all workflow JSON files into n8n  
### 2. Configure credentials  
- Google Drive  
- LLM providers  

### 3. Run the main workflow  
Provide:
- Input images  
- Raw text prompt  

### 4. Outputs  
- Image QA report  
- Multi-platform image variants  
- AI-generated structured copy  

Extend with auto-posting, scheduling, analytics, platform presets, or agentic decision-making.

---

# 🔭 Roadmap

- Auto-posting to Instagram / Facebook / X  
- Scheduling & batch distribution  
- LinkedIn / TikTok / YouTube / Pinterest presets  
- Multi-language content templates  
- Performance analytics feedback  
- Full Agent Mode (format choice + optimization)

---

# 📜 License  
MIT License — free for personal and commercial use.

---

# 📩 Contact

For collaboration or questions:

- **LinkedIn:** https://linkedin.com/in/yourprofile  
- **Email:** yourname.projects@gmail.com  




