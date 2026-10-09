# AI-RESUME-
A Python AI assistant using multiple AI APIs for learning AI and cyber security.
# 📄 AI Resume ATS Checker

A Streamlit app that scores a resume for ATS (Applicant Tracking System) compatibility and gives specific, actionable improvements. Powered by [Groq](https://groq.com) language models.

## Features

- Upload a resume as **PDF or DOCX**
- Optionally paste a **job description** for targeted keyword matching
- **ATS score (0-100)** with a breakdown: keywords, formatting, content quality, impact & metrics
- Strengths, **missing keywords**, and prioritized **improvements** (issue + fix)
- Quick rule-based checks: email, phone, LinkedIn, resume length, standard sections, quantified achievements
- Download the report as JSON

## Project structure

```
.
├── app.py             # Streamlit app
├── requirements.txt   # Python dependencies
└── README.md
```

## Run locally

1. Get a free API key at [console.groq.com](https://console.groq.com).
2. Install and run:

```bash
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

3. Provide your key in **one** of these ways:
   - Environment variable: `export GROQ_API_KEY="your_key"` (Windows PowerShell: `$env:GROQ_API_KEY="your_key"`)
   - File `.streamlit/secrets.toml` containing `GROQ_API_KEY = "your_key"`
   - Or paste it into the sidebar when the app is running

4. Start the app:

```bash
streamlit run app.py
```

## Deploy on Streamlit Community Cloud

1. Push this repo to GitHub (public or private).
2. Go to [share.streamlit.io](https://share.streamlit.io) and sign in with GitHub.
3. Click **Create app**, choose your repository, branch `main`, and main file `app.py`.
4. Open **Advanced settings → Secrets** and add:

```toml
GROQ_API_KEY = "your_key"
```

5. Click **Deploy**.

> Never commit your API key. `.streamlit/secrets.toml` is listed in `.gitignore`.

## Notes and limitations

- The score is an AI-generated estimate, not the output of a real ATS. Treat it as guidance.
- Scanned or image-only resumes can't be read. Use a text-based PDF or DOCX.
- Resumes are truncated to about 12,000 characters before analysis.
- Your resume is sent to Groq for processing and is not stored by this app.
- Models are set in `MODEL_OPTIONS` in `app.py`. If Groq retires a model, update that list (see Groq's model docs).

## License

MIT
