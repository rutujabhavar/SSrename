
# SSrename

SSrename is a Python CLI tool that automatically renames screenshots using OCR-first text extraction with an AI-based fallback for images that lack sufficient readable text.

It is designed to work fully offline using local models and supports both directories and individual image files.

---

## ✨ Features

- OCR-first filename generation using EasyOCR
- Automatic AI fallback using a local Vision-Language Model (BLIP)
- Adaptive OCR thresholds based on screenshot type
  - Code
  - Chat
  - Document
  - Empty
- Works on both directories and single image paths
- Safe preview mode with `--dry-run`
- Collision-safe renaming
- Customizable filename length
- Multiple CLI flags for control and debugging

---

## ⚙️ How It Works

For each image:

1. Extract text using EasyOCR
2. Detect screenshot type
3. Check OCR text threshold
4. If insufficient → generate caption using BLIP
5. Clean and rank keywords
6. Generate meaningful filename
7. Preview or safely apply rename

---

## 📦 Installation

### 1. Clone the repository

```bash
git clone https://github.com/your-username/SSrename.git
cd SSrename
```

### 2. Create and activate virtual environment

```bash
conda create -n ssrename python=3.11
conda activate ssrename
```

### 3. Install package

```bash
pip install -e .
```

---

## 🚀 Usage

### Rename all screenshots in a directory

```bash
ssrename screenshots/ --dry-run
```

### Rename a single image

```bash
ssrename path/to/image.png --dry-run
```

### Limit processing

```bash
ssrename screenshots/ --limit 5 --dry-run
```

### Verbose mode

```bash
ssrename screenshots/ --verbose
```

### OCR only

```bash
ssrename screenshots/ --ocr-only
```

### AI only

```bash
ssrename screenshots/ --ai-only
```

### Control filename length

```bash
ssrename screenshots/ --max-words 3
```

---

## 🧠 Tech Stack

- Python
- EasyOCR
- BLIP
- Transformers
- PIL
- CLI

---

## 📄 License

This project is licensed under the MIT License.

---

## 👨‍💻 Author

Made by [Your Name](https://github.com/yourusername)
