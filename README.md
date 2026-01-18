# YouTube Video Summarizer 🎥📝

[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE) [![Python](https://img.shields.io/badge/python-3.10%2B-blue)](https://www.python.org/) [![Model](https://img.shields.io/badge/model-sshleifer%2Fdistilbart--cnn--12--6-lightgrey)](https://huggingface.co/sshleifer/distilbart-cnn-12-6)

A small Flask web app that fetches a video's transcript using the YouTube Transcript API and generates a short summary using Hugging Face Transformers.

---

## ⚡ Highlights

- Simple web UI to paste a YouTube URL and get an AI-generated summary
- Uses `youtube-transcript-api` to fetch transcripts (English)
- Uses Hugging Face `transformers` (`sshleifer/distilbart-cnn-12-6`) for summarization
- Light-weight, easy to run locally

---

## 🚀 Features

- Paste a YouTube URL into the UI and get a concise summary
- Shows full transcript (collapsible) for reference
- Handles transcripts-disabled errors with a friendly message

---

## 💻 Prerequisites

- Python 3.10+ recommended
- Windows / macOS / Linux

Key dependencies are in `requirements.txt` (e.g., Flask, transformers, youtube-transcript-api).

---

## 🧰 Setup (Windows)

Open PowerShell or Command Prompt and run:

```powershell
# clone the repo
git clone <repo-url>
cd "YouTube Video Summarizer"

# create virtual env
python -m venv env

# activate it (PowerShell)
.\env\Scripts\Activate.ps1
# or (cmd)
# .\env\Scripts\activate.bat

# install dependencies
pip install -r requirements.txt
```

On first run, Transformers will download the model weights (this may take a few minutes).

---

## ▶️ Run the app

```powershell
# while env is activated
python app.py
```

Open http://127.0.0.1:5000 in your browser, paste a YouTube URL (e.g., https://www.youtube.com/watch?v=...) and click "Summarize".

---

## 🔧 Notes & Tips

- The app attempts to fetch English transcripts. If a transcript is not available or is disabled, it will show a warning.
- The app truncates the transcript to the first ~1000 characters before summarizing to keep processing fast. You can modify the truncation in `app.py`.
- Model used: `sshleifer/distilbart-cnn-12-6` (CPU-friendly distilled BART)
- If the page is slow on first run, it's likely downloading the model.

> ⚠️ URL parsing: `app.py` attempts to extract the YouTube video ID from common URL formats (like `watch?v=` and `youtu.be/`). If a URL isn't recognized, an "Invalid YouTube URL" message will appear.

---

## 🧪 Testing

- Try a short video to get fast results.
- If no transcript is found or the transcript is disabled for a given video, the app will flash a warning message.

---

## 🤝 Contributing

Contributions are welcome — open an issue or submit a PR.

---

## 📝 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---
