# NIVA_CHATBOT
# NIVA - Natural Interactive Voice Assistant

<div align="center">
  <img src="https://img.shields.io/badge/Python-3.9%2B-blue" alt="Python Version">
  <img src="https://img.shields.io/badge/license-MIT-green" alt="License">
</div>

![NIVA Interface Preview](./static/screenshot.png)

A multilingual AI voice assistant designed to provide empathetic support and information access for rural Indian communities through natural speech interaction.

## Table of Contents
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [API Documentation](#api-documentation)
- [File Structure](#file-structure)
- [Security](#security)
- [Troubleshooting](#troubleshooting)
- [License](#license)

## Features ✨
- 🎙 Voice-based natural language interaction
- 🌐 Multilingual support (English + Regional Languages)
- 🤖 Gemini-powered AI responses
- 🔊 Real-time text-to-speech conversion
- 📱 Mobile-first responsive design
- 🛡 Privacy-focused audio processing
- 📊 Context-aware responses

## Tech Stack 🛠
*Frontend*  
✔ Modern CSS Grid & Flexbox  
✔ Web Audio API  
✔ MediaRecorder API  
✔ Responsive Design  

*Backend*  
✔ FastAPI Web Framework  
✔ Google Gemini AI  
✔ SpeechRecognition Library  
✔ gTTS Text-to-Speech  

## Installation 💻

### Prerequisites
- Python 3.9+
- Google Cloud API Key
- FFmpeg (Audio Processing)

```bash
# Clone repository
git clone https://github.com/yourusername/niva.git
cd niva

# Install Python dependencies
pip install fastapi uvicorn python-dotenv speechrecognition pydub google-generativeai gtts

# Install FFmpeg (Ubuntu/Debian)
sudo apt install ffmpeg
Configuration ⚙
Create .env file:

env
Copy
GEMINIAPI_KEY=your_google_api_key_here
Obtain Google API Key:

Visit Google AI Studio

Create new project

Enable Gemini API

Generate API key

Usage 🚀
bash
Copy
# Start development server
uvicorn main:app --host 0.0.0.0 --port 3000

# Production deployment (recommended)
uvicorn main:app --host 0.0.0.0 --port 3000 --workers 4 --proxy-headers
Access the interface at: http://localhost:3000

API Documentation 📚
Endpoints
Endpoint	Method	Description
/speech_to_text/	POST	Convert audio to text
/generate-response/	POST	Generate AI response
/text-to-speech/	POST	Convert text to speech
Request Formats
Speech to Text

json
Copy
{
  "file": "audio/webm"
}
Generate Response

json
Copy
{
  "prompt": "user_query"
}
File Structure 📂
Copy
niva/
├── static/
│   ├── styles_v2.css    # Modern CSS styles
│   └── index.html       # Main interface
├── main.py              # Backend server
├── .env                 # Environment config
└── requirements.txt     # Dependencies
Security 🔒
CORS Policy

python
Copy
# Production settings
allow_origins = [
    "https://yourdomain.com",
    "https://api.yourdomain.com"
]
Rate Limiting

10 requests/minute for /generate-response

5 requests/minute for /text-to-speech

Audio Processing

Temporary file cleanup

In-memory processing

No persistent storage

Troubleshooting 🛠
Common Issues

Audio Permission Denied (Linux)

bash
Copy
sudo setfacl -m u:$USER:rw /dev/snd/*
Missing Dependencies

bash
Copy
# Reinstall requirements
pip install --force-reinstall -r requirements.txt
API Key Errors

Verify Google Cloud billing

Check project quota

Enable Gemini API

License 📄
This project is licensed under the MIT License - see the LICENSE file for details.
