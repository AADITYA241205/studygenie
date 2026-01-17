# 📚✨ StudyGenie  
### *Your AI-Powered Personal Study Companion*

> Transform PDFs & images into **summaries, quizzes, flashcards, and an AI tutor** — all in one place.

🚀 **Built at SUNHACKS Hackathon**  
👥 **Team Name:** NameSpace  
🏁 **Achievement:** Finalist (Reached Final Round)

---

## 🧠 What is StudyGenie?

**StudyGenie** is a full-stack, AI-powered web application that converts study documents (PDFs & images) into **interactive learning resources**:

- 📄 Smart summaries  
- 📝 Auto-generated quizzes  
- 🧩 Flashcards with spaced repetition  
- 🤖 A context-aware AI tutor  

It is designed to **reduce study time** and **increase retention** by turning passive reading into active learning.

---

## 🏅 Badges

![Python](https://img.shields.io/badge/Python-3.13%2B-blue)
![Django](https://img.shields.io/badge/Django-4.2-green)
![License](https://img.shields.io/badge/License-MIT-yellow)
![Build](https://img.shields.io/badge/Build-Passing-brightgreen)
![Hackathon](https://img.shields.io/badge/Built%20at-SUNHACKS-orange)

---

## ✨ Feature Highlights

### 📂 Document Upload & Processing
- Supports **PDFs & Images (JPG, PNG)**
- PDF text extraction via **PyPDF2**
- OCR for scanned images using **Tesseract**
- Secure file validation & storage

---

### 🧠 AI-Powered Summaries
- 100–150 word **document-specific summaries**
- Bullet-point key takeaways
- Language-aware generation
- Fallback logic if AI fails

---

### 📝 Dynamic Quiz Generation
- Exactly **10 MCQs per quiz**
- Difficulty levels:
  - 🟢 Easy – Recall & definitions
  - 🟡 Medium – Application & reasoning
  - 🔴 Hard – Analysis & evaluation
- Explanations for every answer
- Stored quiz history & scoring

---

### 🧩 Flashcards with Spaced Repetition
- 8–12 flashcards per document
- Optimized for quick recall
- Tracks cards that need revision

---

### 🤖 AI Tutor (Chat Assistant)
- Ask questions in natural language
- Answers based **only on your uploaded documents**
- Maintains conversation history
- Perfect for last-minute doubts

---

### 🌍 Multi-Language Support
Supported languages:
- English
- Hindi
- Marathi
- Spanish
- French
- German

Includes automatic language detection and translation.

---

### 📊 Progress Tracking
- Learning streaks 🔥
- Quiz performance analytics
- Flashcards reviewed
- Documents uploaded

---

## 🖼️ Screenshots & Demo

> 📌 **Add screenshots here**
- Dashboard overview
- Document upload page
- Quiz interface
- Flashcard review
- AI tutor chat

*(Screenshots/GIFs greatly improve GitHub visibility)*

---

## 🛠️ Tech Stack

### Backend
- **Django 4.2**
- Python 3.13+

### AI Engine
- **Google Gemini 1.5 Flash API**

### Frontend
- HTML5, CSS3
- Bootstrap 5
- Vanilla JavaScript

### Database
- SQLite (development)
- PostgreSQL (production-ready)

### Document Processing
- PyPDF2 (PDF text extraction)
- Pytesseract + Pillow (OCR)

---

## 📁 Project Structure

```
studygenie/
├── authentication/
├── dashboard/
├── documents/
├── quizzes/
├── flashcards/
├── static/
├── templates/
├── media/documents/
├── studygenie/
├── ai_services.py
├── create_users.py
├── manage.py
├── requirements.txt
├── .env.example
├── setup.bat
└── run_server.bat
```

---

## ⚙️ Installation & Setup
### 🔑 Prerequisites
- Python 3.13+
- Google AI API Key  👉 https://makersuite.google.com/app/apikey
- Tesseract OCR installed

### 🚀 Quick Setup (Windows)
```
setup.bat
```
1. Add your API key in .env
2. Run:
```
run_server.bat
```

### 🧑‍💻 Manual Setup
```
git clone <repository-url>
cd studygenie
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```
Create .env:
```
GOOGLE_AI_API_KEY=your_api_key_here
```
Run:
```
python manage.py migrate
python create_users.py
python manage.py runserver
```
### 🔐 Demo Credentials
| Role  | Username | Password    |
| ----- | -------- | ----------- |
| User  | demo     | demo123     |
| User  | student1 | password123 |
| Admin | admin    | admin123    |

---

## 🔌 AI Services API (Core Functions)
```
generate_summary_with_ai(text, length="medium")
generate_quiz_with_ai(text, difficulty="medium")
generate_flashcards_with_ai(text)
detect_language(text)
translate_content(text, target_language)
```
Powered by:
```
gemini-1.5-flash
```

---

## 🧪 Workflow
```
Login → Upload Document → Text Extraction
        ↓
      AI Processing
        ↓
 Summary + Quiz + Flashcards
        ↓
 Study → Practice → Review → Ask AI Tutor
        ↓
 Progress Tracking & Analytics
```

---

## 🎯 Use Cases
- 🎓 Students – Convert notes into study material
- 👨‍🏫 Educators – Generate quizzes instantly
- 👨‍💻 Professionals – Learn from technical docs
- 📚 Researchers – Summarize academic papers
- 🌍 Language learners – Multilingual study support

---

## 🔐 Security
- Environment variables for secrets
- CSRF protection
- Auth-guarded routes
- File upload validation
- Django ORM (SQL injection safe)

---

## 🛣️ Roadmap
- 🔊 Voice-based AI tutor
- 📱 Mobile-responsive PWA
- 📈 Advanced analytics
- 📤 Export quizzes & flashcards
- 🤝 Collaborative study rooms

---

## 🤝 Contributing
Contributions are welcome!
Please see:
- CONTRIBUTING.md
- Issue & PR templates

---

## 📜 License
This project is licensed under the MIT License.

---

## 🙏 Acknowledgments
- SUNHACKS Hackathon for the platform
- Team NameSpace 💙
- Google Gemini API
- Django & Open-source community

---

## 📬 Contact & Support
👤 Aaditya Siddharth Bansod
🔗 GitHub: https://github.com/AADITYA241205
💼 LinkedIn: (https://www.linkedin.com/in/aaditya-siddharth-bansod-889590333/)

Made with ❤️ for students everywhere
