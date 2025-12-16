# Markdown + Pandoc Document Template

This repository provides a reusable **Markdown document skeleton** designed to be compiled with **Pandoc**.  
It is intended as a launchpad for reports, academic writing, teaching materials, and other structured documents.

The benefit of using Pandoc is that it lets you write Markdown documents made up of
separate, well-organised sections, while also handling citations and reference lists
automatically.

---

## ✨ Features

- Modular document structure (each section in its own file)
- Single-command build using Pandoc
- Clean separation of:
  - Metadata
  - Content
  - Output formats
- Easy to extend to PDF, HTML, or DOCX

---

## 📁 Directory Structure

```text
.
├── README.md
├── LICENSE
├── description.yaml
├── bibliography/ 
│   └── bibliography.bib
├── sections/
│   ├── 001-intro.md
│   ├── 997-conclusion.md
│   ├── 998-bibliography.md
│   └── 999-appendix.md
└── build/
````

### Description

* **`description.yaml`**
  Document metadata (title, author, date, etc.)

* **`bibliography/`**
  Bibliography file in the BibTex format.

* **`sections/`**
  Individual Markdown files for each logical section of the document.
  Numbering is optional but helps enforce ordering.

* **`build/`**
  Output directory for generated files (PDF, HTML, DOCX, etc.)

---

## 🧱 Writing Content

Each section is written as normal Markdown:

```markdown
# Introduction

This section introduces the topic and sets context for the document.
```

Avoid repeating top-level metadata (title, author) inside section files.

---

## 🔧 Building the Document

```bash
pandoc description.yaml sections/*.md --standalone --citeproc --bibliography=./bibliography/bibliography.bib --csl=./bibliography/styles/harvard-university-of-leeds.csl -o ./build/paper.pdf
```

Pandoc treats all input files as a single document in the order provided.

---

## 📤 Output Formats

Pandoc can target multiple formats from the same source:

```bash
pandoc metadata.yaml sections/*.md -o build/output.pdf
pandoc metadata.yaml sections/*.md -o build/output.docx
pandoc metadata.yaml sections/*.md -o build/output.html
```

You can also add templates, reference documents, or CSS later as needed.


## 🚀 Getting Started

1. Clone or copy this repository
2. Update `description.yaml`
3. Rename or add files in `sections/`
4. Build using Pandoc

That’s it.

---

## 📄 Requirements

* [Pandoc](https://pandoc.org/)


