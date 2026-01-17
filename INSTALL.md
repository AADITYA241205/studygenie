# Installation Guide

Complete setup instructions for StudyGenie across different platforms.

## Table of Contents
- [Windows Setup](#windows-setup)
- [Linux/macOS Setup](#linuxmacos-setup)
- [Docker Setup](#docker-setup)
- [Troubleshooting](#troubleshooting)

## Windows Setup

### Prerequisites
1. Python 3.13+ ([Download](https://www.python.org/downloads/))
2. Git ([Download](https://git-scm.com/download/win))
3. Tesseract OCR ([Download](https://github.com/UB-Mannheim/tesseract/wiki))

### Quick Start (Automated)
```bash
# Clone the repository
git clone https://github.com/yourusername/studygenie.git
cd studygenie

# Run setup script
setup.bat

# Add your API key to .env file
notepad .env

# Start the server
run_server.bat
```

### Manual Setup
```bash
# 1. Clone repository
git clone https://github.com/yourusername/studygenie.git
cd studygenie

# 2. Create virtual environment
python -m venv venv
venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Setup environment
copy .env.example .env
# Edit .env and add your Google AI API key

# 5. Setup database
python manage.py makemigrations
python manage.py migrate

# 6. Create demo users
python create_users.py

# 7. Run server
python manage.py runserver
```

## Linux/macOS Setup

### Prerequisites
```bash
# Ubuntu/Debian
sudo apt update
sudo apt install python3.13 python3-pip python3-venv tesseract-ocr git

# macOS (using Homebrew)
brew install python@3.13 tesseract git
```

### Installation
```bash
# 1. Clone repository
git clone https://github.com/yourusername/studygenie.git
cd studygenie

# 2. Create virtual environment
python3 -m venv venv
source venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Setup environment
cp .env.example .env
# Edit .env: nano .env or vim .env

# 5. Setup database
python manage.py makemigrations
python manage.py migrate

# 6. Create demo users
python create_users.py

# 7. Run server
python manage.py runserver
```

## Docker Setup

### Prerequisites
- Docker ([Download](https://www.docker.com/products/docker-desktop))
- Docker Compose

### Using Docker Compose
```bash
# 1. Clone repository
git clone https://github.com/yourusername/studygenie.git
cd studygenie

# 2. Create .env file
cp .env.example .env
# Edit .env and add your API key

# 3. Build and run
docker-compose up --build

# 4. Access at http://localhost:8000
```

### Using Docker Only
```bash
# Build image
docker build -t studygenie .

# Run container
docker run -p 8000:8000 --env-file .env studygenie
```

## Configuration

### Google AI API Key
1. Visit https://makersuite.google.com/app/apikey
2. Create a new API key
3. Add to `.env` file:
   ```
   GOOGLE_AI_API_KEY=your-api-key-here
   ```

### Tesseract OCR Path (Windows)
If Tesseract is not in PATH, add to `.env`:
```
TESSERACT_PATH=C:\Program Files\Tesseract-OCR\tesseract.exe
```

## Troubleshooting

### "Module not found" Error
```bash
pip install -r requirements.txt
```

### Database Migration Issues
```bash
python manage.py makemigrations --empty appname
python manage.py migrate
```

### Port Already in Use
```bash
# Use different port
python manage.py runserver 8080
```

### Tesseract Not Found
- Windows: Add Tesseract to PATH or set TESSERACT_PATH in .env
- Linux: `sudo apt install tesseract-ocr`
- macOS: `brew install tesseract`

### API Key Issues
- Verify key is correct in `.env`
- Check API quota at Google AI Studio
- Ensure `.env` file is in project root

## First Run

After setup, access the application at:
```
http://127.0.0.1:8000
```

Login with demo credentials:
- Username: `demo`
- Password: `demo123`

## Production Deployment

For production:
1. Set `DEBUG=False` in `.env`
2. Generate new `DJANGO_SECRET_KEY`
3. Update `ALLOWED_HOSTS`
4. Use proper database (PostgreSQL)
5. Setup HTTPS
6. Configure static files serving
7. Use production WSGI server (Gunicorn)

## Support

For issues:
- Check [Troubleshooting](#troubleshooting)
- Open an issue on GitHub
- Review documentation

---

Happy studying! 🎓
