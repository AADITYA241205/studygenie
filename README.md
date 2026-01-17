# StudyGenie - AI-Powered Study Companion 🧞♂️

Transform your documents into interactive study materials with AI-powered summaries, quizzes, flashcards, and an intelligent tutor.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/python-3.13+-blue.svg)](https://www.python.org/downloads/)
[![Django](https://img.shields.io/badge/django-4.2-green.svg)](https://www.djangoproject.com/)

## 🚀 Features

- **Smart Document Upload** - PDFs and images with OCR support
- **AI-Generated Summaries** - Powered by Google Gemini AI
- **Dynamic Quizzes** - Contextual MCQs with multiple difficulty levels
- **Interactive Flashcards** - Spaced repetition system for effective learning
- **AI Tutor Chat** - Ask questions about your study materials
- **Progress Analytics** - Track learning streaks and quiz scores
- **Multi-language Support** - Summaries in English, Hindi, Marathi, and more

## 📋 Prerequisites

- Python 3.13 or higher
- Google AI API key ([Get one here](https://makersuite.google.com/app/apikey))
- Tesseract OCR (for image text extraction)

## ⚡ Quick Setup

### Option 1: Automated Setup (Windows)

```bash
# Run the setup script
setup.bat

# Add your Google AI API key to .env
# Then start the server
run_server.bat
```

### Option 2: Manual Setup

```bash
# 1. Clone the repository
git clone https://github.com/yourusername/studygenie.git
cd studygenie

# 2. Install dependencies
pip install -r requirements.txt

# 3. Set up environment variables
copy .env.example .env
# Edit .env and add your Google AI API key

# 4. Setup database
python manage.py makemigrations
python manage.py migrate

# 5. Create demo users
python create_users.py

# 6. Start the development server
python manage.py runserver
```

## 🔑 Login Credentials

After running `create_users.py`, use these credentials:

- **Demo User**: `demo` / `demo123`
- **Student**: `student1` / `password123`
- **Admin**: `admin` / `admin123`

## 📖 Usage Guide

1. **Login** → Use any of the demo credentials
2. **Upload** → Select PDF or image file (study notes, textbooks, etc.)
3. **Study** → View AI-generated summary of your material
4. **Practice** → Take personalized quizzes with adjustable difficulty
5. **Review** → Use flashcards with spaced repetition
6. **Ask** → Chat with AI tutor about specific questions
7. **Track** → Monitor progress and learning streaks

## 🛠 Tech Stack

- **Backend**: Django 4.2, SQLite
- **Frontend**: Bootstrap 5, JavaScript
- **AI**: Google Gemini 1.5 Flash
- **Processing**: PyPDF2, Pytesseract OCR
- **Deployment**: Python 3.13+

## 🌟 Key Workflows

### Document Processing Pipeline

```
Upload → Text Extraction → AI Processing → Content Generation
   ↓           ↓              ↓              ↓
 PDF/IMG → OCR/Parse → Gemini API → Summary/Quiz/Cards
```

### AI-Powered Features

- **Summaries**: Contextual, structured content overviews (100-150 words)
- **Quizzes**: Auto-generated MCQs with 3 difficulty levels (Easy/Medium/Hard)
- **Flashcards**: Key terms and definitions extraction
- **Tutor**: Context-aware Q&A using document content

## 🔧 Configuration

### Google AI API Setup

1. Get API key: https://makersuite.google.com/app/apikey
2. Add to `.env`: `GOOGLE_AI_API_KEY=your-api-key-here`
3. Restart server

### Admin Panel

- URL: http://127.0.0.1:8000/admin/
- Manage users, documents, quizzes, and progress

## 📁 Project Structure

```
studygenie/
├── authentication/      # User authentication
├── dashboard/          # Main dashboard and AI assistant
├── documents/          # Document upload and processing
├── flashcards/         # Flashcard generation and review
├── quizzes/           # Quiz generation and taking
├── static/            # CSS, JS, images
├── templates/         # HTML templates
├── media/             # Uploaded documents
├── ai_services.py     # AI integration (Gemini)
├── create_users.py    # Demo user creation script
└── manage.py          # Django management
```

## 🎯 Perfect For

- **Students** - Convert textbooks into study materials
- **Educators** - Create quizzes from course content
- **Professionals** - Learn from technical documents
- **Researchers** - Summarize academic papers

## 🤝 Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Google Gemini AI for powerful language processing
- Django community for the excellent framework
- Bootstrap for responsive UI components

## 📧 Support

For issues and questions:
- Open an issue on GitHub
- Check existing documentation
- Review the code comments

---

Made with ❤️ for students everywhere
