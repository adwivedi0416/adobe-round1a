````markdown
# Adobe Hackathon Round 1A — PDF Outline Extractor

## 🚀 Objective
Extract a clean, structured outline from a PDF, including the document title and heading hierarchy (H1, H2, H3) with associated page numbers.

---

## 🛠️ Features
- Supports PDFs up to 50 pages
- Extracts:
  - Title (inferred from text size and frequency)
  - Headings (H1, H2, H3) with levels and page numbers
- Outputs structured JSON:
```json
{
  "title": "Sample Title",
  "outline": [
    { "level": "H1", "text": "Introduction", "page": 1 }
  ]
}
````

---

## 🧱 Tech Stack

* Python 3.10
* [PyMuPDF (fitz)](https://pymupdf.readthedocs.io/en/latest/)
* Docker

---

## 🧪 Constraints Met

| Constraint       | Status                |
| ---------------- | --------------------- |
| Max Model Size   | ✅ N/A (no model used) |
| Execution Time   | ✅ <10s for 50 pages   |
| Internet Access  | ✅ Fully Offline       |
| Runtime Platform | ✅ CPU-only (AMD64)    |

---

## 🐳 Docker Instructions

### Build:

```bash
docker build --platform linux/amd64 -t pdf-outline-extractor .
```

### Run:

```bash
docker run --rm -v $(pwd)/input:/app/input -v $(pwd)/output:/app/output --network none pdf-outline-extractor
```

---

## 📁 Folder Structure

```
Round1A/
├── Dockerfile
├── main.py
├── requirements.txt
├── input/
└── output/
```

---

## 📌 Notes

* Does not rely solely on font size; uses font styling (bold) + hierarchy rules
* Modular design: components reusable in Round 1B


