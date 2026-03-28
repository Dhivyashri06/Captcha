# CAPTCHA AI

An AI-powered CAPTCHA generation, verification, and breaking system using LLMs and an agent-based architecture. This project demonstrates how modern AI models can be combined with traditional OCR techniques to build intelligent and fault-tolerant systems.

---

##  Overview

CAPTCHA AI is a modular system that:
- Generates secure CAPTCHA challenges  
- Verifies user responses  
- Attempts to break CAPTCHAs using AI (Gemini) with OCR fallback  

It uses an **agent-based workflow (LangGraph)** to dynamically select tools and perform reasoning.

---

##  Features

- AI-generated CAPTCHA text using Gemini API  
- Dynamic CAPTCHA image generation with noise and distortion  
- Secure CAPTCHA verification using unique IDs  
- AI-based CAPTCHA solving using Gemini  
- OCR fallback using Tesseract  
- Agent-based tool selection using LangGraph (ReAct pattern)  
- Modular architecture using MCP (Model Context Protocol)  
- Asynchronous execution using asyncio  

---

##  Architecture

```

User Input
↓
LangGraph Agent
↓
MCP Client (Tool Selection)
↓
MCP Server (Captcha Tools)
↓
Gemini API / OCR
↓
Response

````

---

## Tech Stack

- Python  
- Google Gemini API  
- LangGraph  
- LangChain  
- FastMCP  
- Pillow  
- Pytesseract  
- AsyncIO  

---

## Setup

### 1. Clone Repository
```bash
git clone https://github.com/Dhivyashri06/captcha-ai.git
cd captcha-ai
````

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Install Tesseract

**Windows:** Install and add to PATH
**Linux:**

```bash
sudo apt install tesseract-ocr
```

**Mac:**

```bash
brew install tesseract
```

### 4. Create `.env` File

```
GOOGLE_API_KEY=your_api_key_here
```

---

## Run

### Start Server

```bash
python mcp_server.py
```

### Start Client

```bash
python main.py
```

---

## Example Usage

```
Generate a captcha  
Verify captcha  
Break captcha  
```

---

## Tools

### generate_captcha()

Returns:

* CAPTCHA ID
* Text
* Base64 Image

### verify_captcha(captcha_id, user_input)

Returns:

* Correct / Wrong

### break_captcha(captcha_image_base64)

Returns:

* Predicted text
* Source (Gemini / OCR)

