# W8BDCR-Vercel-OCR

OCR API on Vercel (serverless). Send a base64 image, get the text back — Bengali + English.

## How it works

Serverless function (`api/ocr.py`) running Tesseract OCR (`ben+eng`, `--psm 7`). `install.sh` installs Tesseract with Bengali and English language data at build time.

## API

`POST /api/ocr`

```json
{ "image": "<base64-encoded image>" }
```

Returns `{"text": "..."}`. POST only — other methods return `{"error": "POST only"}`.

## Deploy

Push to Vercel — `vercel.json` wires the build (`bash install.sh`) and the Python runtime.
