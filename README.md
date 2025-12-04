# auto-publishing-agent-n8n
A modular n8n-based Auto Publishing Agent for creators and teams. It includes image quality checking, multi-platform image adaptation, and AI-powered copywriting. Designed to standardize the publishing workflow so people can focus on differentiating their own products and services.

# Auto Publishing Agent (n8n Workflow)
### Standardize Promotion · Strengthen Product Differentiation

A modular, extensible **Auto Publishing Agent** built with n8n.  
This project automates the *mechanical and repetitive* parts of promotion — image preparation, platform adaptation, metadata generation, and AI copywriting — so creators, teams, and businesses can invest their time where it truly matters:

## **Building differentiated products and delivering differentiated services.**

Promotion should not drain the energy needed for innovation.  
Expression should not be a barrier to value delivery.  
Automation should remove friction, not add complexity.

This repository contains:
- A main workflow  
- Two sub-workflows (ImageEdit + TextEdit)  
Together forming a full, production-oriented publishing pipeline.

---

# 🌍 Purpose & Philosophy

In the modern landscape, products and services become valuable because of their **uniqueness**, not because their creators spend hours fighting platform rules and formatting requirements.

Yet most creators face the same bottleneck:

> **Publishing is unnecessarily complex, inconsistent, and time-consuming.**

People repeatedly spend time learning:
- Different aspect ratio requirements across platforms  
- How to crop and resize correctly  
- Best practices for formats and resolutions  
- How to rewrite copy for each platform  

These tasks **do not contribute to the differentiation of the product itself**.

This project aims to shift the balance:

# 👉 **Standardize and automate promotion.  
Let creators focus on the differentiated value only they can produce.**

---

# 🚀 Features Overview

## ✔ 1. Main Image Quality Check (QA Engine)

Evaluates uploaded images to ensure they meet modern social media standards:

- Detects width, height, and aspect ratio  
- Verifies portrait orientation  
- Detects 4:5 ratio tolerance (±0.04)  
- Ensures minimum short-edge resolution  
- Outputs classification: `high / ok / low / none`  
- Provides human-readable explanations for pass/fail  

*(Workflow: `P001_AutomaticallyPublishWorks.json`)*

---

## ✔ 2. Multi-Platform Image Adaptation (Preset Engine)

Automatically generates platform-ready image variants.

Supported presets:

| Platform | Ratios |
|----------|--------|
| Instagram | 1:1, 4:5, 9:16 |
| Facebook | 1:1, 4:5, 9:16, 16:9 |
| X/Twitter | 1:1, 16:9 |

Features:
- Smart center cropping  
- Boundary protections  
- Size normalization for recommended resolutions  
- Structured file naming (`B[batch]__I[index]__P[preset]`)  
- Upload to Google Drive  

*(Workflow: `P001_sub_ImageEdit.json`)*

This removes the repetitive design work required to prepare assets for multiple platforms.

---

## ✔ 3. AI Copywriting Pipeline (Structured Output)

Given a raw prompt, generates consistent, platform-ready promotional text.

Outputs include:
- Platform  
- Title  
- Keywords  
- Polished content  

Highlights:
- Supports OpenAI, Gemini, and OpenRouter  
- Multi-language (EN / ZH)  
- Round-robin model selection  
- Strict JSON schema validation  

*(Workflow: `P001_sub_TextEdit.json`)*

This produces clean, repeatable, structured content suitable for automated publishing.

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

This modular design makes it easy to extend, replace modules, or integrate into a larger agent system.

---

# 📦 Repository Structure

```
.
├── README.md
├── P001_AutomaticallyPublishWorks.json
├── P001_sub_ImageEdit.json
└── P001_sub_TextEdit.json
```

---

# 🛠 Requirements

- n8n (self-hosted or cloud)
- Google Drive OAuth2 credentials
- One or more LLM providers:
  - OpenAI  
  - Gemini  
  - OpenRouter  

---

# 📥 Installation & Usage

### 1. Import workflows  
Import all three JSON files into n8n.

### 2. Configure credentials  
Set:
- Google Drive  
- LLM provider(s)

### 3. Run the main workflow  
Provide:
- One or more images  
- A text prompt  

### 4. Outputs  
- Image quality report  
- Platform-ready images  
- AI-generated structured copy  

From here you may extend the pipeline with:
- Auto-posting  
- Scheduling  
- Additional platforms  
- Analytics feedback  

---

# 📸 Screenshots (Replace with Your Own)

```
[Main workflow screenshot]
```
```
[ImageEdit subworkflow screenshot]
```
```
[TextEdit subworkflow screenshot]
```
```
[Generated images screenshot]
```

---

# 🔭 Roadmap

- Automatic publishing to major platforms  
- Scheduling and posting queues  
- More presets (LinkedIn, TikTok, YouTube, Pinterest)  
- Multi-language text generation  
- Performance analytics integration  
- Full “Agent Mode”:
  - Selecting formats  
  - Generating variants  
  - Learning from performance metrics  

---

# 📜 License

MIT License — free for commercial and personal use.

---

# 🙌 Contribute

You are welcome to fork the repository, extend presets, refine prompts, or build posting modules.

---

# 📩 Contact

For collaboration, discussion, or questions about automation and publishing systems, feel free to reach out.


