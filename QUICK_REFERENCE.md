# StudyGenie - Quick Reference Card

## 🚀 Quick Start Commands

### First Time Setup
```bash
# Clone repository
git clone https://github.com/YOUR_USERNAME/studygenie.git
cd studygenie

# Setup (Windows)
setup.bat

# Setup (Linux/Mac)
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
# Edit .env and add your API key
python manage.py migrate
python create_users.py
python manage.py runserver
```

### Daily Development
```bash
# Activate virtual environment
# Windows: venv\Scripts\activate
# Linux/Mac: source venv/bin/activate

# Run server
python manage.py runserver

# Access at: http://127.0.0.1:8000
```

## 🔑 Demo Credentials

| Username  | Password    | Role  |
|-----------|-------------|-------|
| demo      | demo123     | User  |
| student1  | password123 | User  |
| admin     | admin123    | Admin |

## 📁 Important Files

| File | Purpose |
|------|---------|
| `.env` | Your API keys (NEVER commit!) |
| `.env.example` | Template for environment variables |
| `requirements.txt` | Python dependencies |
| `manage.py` | Django management commands |
| `create_users.py` | Create demo users |
| `ai_services.py` | AI integration logic |

## 🛠️ Common Django Commands

```bash
# Database
python manage.py makemigrations
python manage.py migrate
python manage.py createsuperuser

# Server
python manage.py runserver
python manage.py runserver 8080  # Different port

# Shell
python manage.py shell

# Static files
python manage.py collectstatic

# Check for issues
python manage.py check
```

## 📦 Git Commands

```bash
# Initial setup
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/USER/studygenie.git
git push -u origin main

# Daily workflow
git status                    # Check changes
git add .                     # Stage all changes
git commit -m "Description"   # Commit changes
git push                      # Push to GitHub
git pull                      # Pull latest changes

# Branching
git checkout -b feature-name  # Create branch
git checkout main             # Switch to main
git merge feature-name        # Merge branch
```

## 🐛 Troubleshooting

| Problem | Solution |
|---------|----------|
| Module not found | `pip install -r requirements.txt` |
| Port in use | `python manage.py runserver 8080` |
| Database error | `python manage.py migrate` |
| API key error | Check `.env` file has correct key |
| Tesseract error | Install Tesseract OCR |

## 🔗 Quick Links

- **Google AI API**: https://makersuite.google.com/app/apikey
- **Django Docs**: https://docs.djangoproject.com
- **Git Docs**: https://git-scm.com/doc
- **Python Docs**: https://docs.python.org

## 📚 Documentation Files

- `README.md` - Main documentation
- `INSTALL.md` - Installation guide
- `ARCHITECTURE.md` - Technical details
- `CONTRIBUTING.md` - How to contribute
- `GITHUB_SETUP.md` - GitHub upload guide
- `SECURITY.md` - Security policy

## 🎯 Project URLs

```
Homepage:     http://127.0.0.1:8000/
Login:        http://127.0.0.1:8000/auth/login/
Dashboard:    http://127.0.0.1:8000/dashboard/
Admin:        http://127.0.0.1:8000/admin/
Documents:    http://127.0.0.1:8000/documents/
Quizzes:      http://127.0.0.1:8000/quizzes/
Flashcards:   http://127.0.0.1:8000/flashcards/
```

## 🔐 Environment Variables

```bash
# Required
GOOGLE_AI_API_KEY=your-api-key-here

# Optional (for production)
DJANGO_SECRET_KEY=your-secret-key
DEBUG=False
ALLOWED_HOSTS=yourdomain.com
```

## 🐳 Docker Commands

```bash
# Build and run
docker-compose up --build

# Run in background
docker-compose up -d

# Stop containers
docker-compose down

# View logs
docker-compose logs -f
```

## 📊 Project Stats

- **Language**: Python 3.13+
- **Framework**: Django 4.2
- **AI Model**: Google Gemini 1.5 Flash
- **Database**: SQLite (dev) / PostgreSQL (prod)
- **Frontend**: Bootstrap 5 + JavaScript
- **License**: MIT

## 🎓 Features

- ✅ PDF & Image upload
- ✅ AI summaries
- ✅ Dynamic quizzes (3 difficulty levels)
- ✅ Flashcards with spaced repetition
- ✅ AI tutor chat
- ✅ Progress tracking
- ✅ Multi-language support
- ✅ User authentication

## 💡 Tips

1. Always activate virtual environment before working
2. Never commit `.env` file
3. Test locally before pushing to GitHub
4. Write clear commit messages
5. Update documentation when adding features
6. Use branches for new features
7. Keep dependencies updated
8. Follow the code style

---

**Need more help?** Check the full documentation files!
