# Smart Email Assistant 🤖

A Chrome Extension that integrates directly into Gmail to generate tone-aware, AI-powered email replies using Google Gemini API and a Spring Boot backend.

## Architecture
Chrome Extension (Frontend) → Spring Boot REST API (Backend) → Google Gemini API (LLM)

## Tech Stack
- **Backend:** Java, Spring Boot, Spring AI, REST APIs
- **Frontend:** JavaScript, Chrome Extension API
- **AI:** Google Gemini API, Prompt Engineering
- **Tools:** Maven, Git

## Features
- 🧠 Generates context-aware email replies inside Gmail
- 🎯 Tone selection — Professional, Casual, Formal
- ⚡ Real-time AI response injection into Gmail's compose window
- 🔌 Decoupled backend architecture — swap LLM models easily

## How It Works
1. Open any email in Gmail
2. Click the Smart Reply button injected by the extension
3. Select your preferred tone
4. Extension sends email context to Spring Boot backend
5. Backend constructs prompt and calls Gemini API
6. AI-generated reply is injected directly into Gmail compose box

## Getting Started

### Prerequisites
- Java 17+
- Maven
- Google Gemini API key
- Chrome browser

### Backend Setup
```bash
git clone https://github.com/Navendu07/smart-email-assistant
cd smart-email-assistant/backend
# Add your Gemini API key in application.properties
# gemini.api.key=YOUR_API_KEY
mvn spring-boot:run
```

### Chrome Extension Setup
1. Open Chrome → chrome://extensions
2. Enable Developer Mode
3. Click Load Unpacked
4. Select the /extension folder from this repo
5. Open Gmail and start using Smart Reply

## Project Structure
```
smart-email-assistant/
├── backend/
│   ├── src/main/java/
│   │   ├── controller/    # REST endpoints
│   │   ├── service/       # Gemini API integration
│   │   └── model/         # Request/Response models
│   └── pom.xml
├── extension/
│   ├── manifest.json
│   ├── content.js         # Gmail DOM injection
│   └── popup.js
└── README.md
```

## API Reference
```
POST /api/email/generate-reply
Content-Type: application/json

{
  "emailContent": "Original email text here",
  "tone": "professional"
}
```

## Author
**Navendu Shekhar Ojha**
- GitHub: https://github.com/Navendu07
- LinkedIn: https://linkedin.com/in/navendu-ojha
- Portfolio: https://navendu-portfolio.vercel.app
