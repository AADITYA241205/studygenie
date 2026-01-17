# StudyGenie Architecture

Technical documentation for developers and contributors.

## System Architecture

```
┌─────────────────────────────────────────────────────────┐
│                     User Interface                       │
│              (Bootstrap 5 + JavaScript)                  │
└────────────────────┬────────────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────────────┐
│                  Django Backend                          │
│  ┌──────────┬──────────┬──────────┬──────────────────┐ │
│  │   Auth   │Documents │ Quizzes  │   Flashcards     │ │
│  └──────────┴──────────┴──────────┴──────────────────┘ │
└────────────────────┬────────────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────────────┐
│              AI Services Layer                           │
│         (Google Gemini 1.5 Flash)                       │
│  ┌──────────┬──────────┬──────────┬──────────────────┐ │
│  │ Summary  │  Quiz    │Flashcard │   Translation    │ │
│  │Generator │Generator │Generator │    Service       │ │
│  └──────────┴──────────┴──────────┴──────────────────┘ │
└────────────────────┬────────────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────────────┐
│            Document Processing                           │
│  ┌──────────────────┬──────────────────────────────┐   │
│  │  PDF Extraction  │    OCR Processing            │   │
│  │    (PyPDF2)      │    (Pytesseract)             │   │
│  └──────────────────┴──────────────────────────────┘   │
└─────────────────────────────────────────────────────────┘
```

## Project Structure

```
studygenie/
├── authentication/          # User authentication & authorization
│   ├── views.py            # Login/logout views
│   └── urls.py             # Auth URL routing
│
├── dashboard/              # Main dashboard & AI assistant
│   ├── views.py            # Dashboard views
│   ├── ai_assistant.py     # AI tutor chat logic
│   └── models.py           # Progress tracking models
│
├── documents/              # Document management
│   ├── models.py           # Document model
│   ├── views.py            # Upload, view, delete
│   └── migrations/         # Database migrations
│
├── quizzes/                # Quiz system
│   ├── models.py           # Quiz & Question models
│   ├── views.py            # Quiz generation & taking
│   └── migrations/         # Database migrations
│
├── flashcards/             # Flashcard system
│   ├── models.py           # Flashcard model
│   ├── views.py            # Flashcard CRUD & review
│   └── migrations/         # Database migrations
│
├── static/                 # Static assets
│   ├── css/               # Stylesheets
│   ├── js/                # JavaScript files
│   └── images/            # Images
│
├── templates/              # HTML templates
│   ├── registration/      # Login templates
│   ├── dashboard/         # Dashboard templates
│   ├── documents/         # Document templates
│   ├── quizzes/          # Quiz templates
│   └── flashcards/       # Flashcard templates
│
├── media/                  # User uploads
│   └── documents/         # Uploaded documents
│
├── studygenie/            # Project settings
│   ├── settings.py        # Django configuration
│   ├── urls.py            # Main URL routing
│   └── wsgi.py            # WSGI config
│
├── ai_services.py         # AI integration module
├── create_users.py        # Demo user creation
├── manage.py              # Django management
└── requirements.txt       # Python dependencies
```

## Core Components

### 1. Document Processing Pipeline

**Flow:**
```
Upload → Validation → Text Extraction → AI Processing → Storage
```

**Key Functions:**
- `extract_text_from_pdf()` - PDF text extraction
- `extract_text_from_image()` - OCR processing
- `generate_summary_with_ai()` - AI summary generation

### 2. AI Services (ai_services.py)

**Main Functions:**

```python
# Summary Generation
generate_summary_with_ai(text, length="medium")
generate_summary_with_language(text, language, length="medium")

# Quiz Generation
generate_quiz_with_ai(text, difficulty='medium')
generate_quiz_with_language(text, language='en', difficulty='medium')

# Flashcard Generation
generate_flashcards_with_ai(text)
generate_flashcards_with_language(text, language='en')

# Translation
translate_content(text, target_language)
```

**Difficulty Levels:**
- Easy: Factual recall, definitions
- Medium: Application, analysis
- Hard: Evaluation, synthesis

### 3. Database Models

**Document Model:**
```python
class Document(models.Model):
    user = ForeignKey(User)
    title = CharField(max_length=200)
    file = FileField(upload_to='documents/')
    extracted_text = TextField()
    summary = TextField()
    detected_language = CharField(max_length=10)
    uploaded_at = DateTimeField(auto_now_add=True)
```

**Quiz Model:**
```python
class Quiz(models.Model):
    document = ForeignKey(Document)
    title = CharField(max_length=200)
    difficulty = CharField(max_length=20)
    language = CharField(max_length=10)
    created_at = DateTimeField(auto_now_add=True)
```

**Question Model:**
```python
class Question(models.Model):
    quiz = ForeignKey(Quiz)
    stem = TextField()
    options = JSONField()
    answer_key = CharField(max_length=1)
    explanation = TextField()
```

**Flashcard Model:**
```python
class Flashcard(models.Model):
    document = ForeignKey(Document)
    front = CharField(max_length=200)
    back = TextField()
    language = CharField(max_length=10)
```

## API Integration

### Google Gemini AI

**Configuration:**
```python
import google.generativeai as genai
genai.configure(api_key=os.getenv('GOOGLE_AI_API_KEY'))
model = genai.GenerativeModel('gemini-1.5-flash')
```

**Usage:**
```python
response = model.generate_content(prompt)
result = response.text
```

## Key Features Implementation

### 1. Multi-language Support
- Language detection using Unicode ranges
- Translation via Gemini API
- Supported: English, Hindi, Marathi, Spanish, French, German

### 2. Dynamic Quiz Generation
- Context-aware question generation
- Three difficulty levels
- Automatic distractor generation
- Explanation for each answer

### 3. Spaced Repetition
- Flashcard review system
- Progress tracking
- Difficulty adjustment

### 4. AI Tutor
- Document-context aware responses
- Natural language processing
- Follow-up question handling

## Security Considerations

1. **File Upload Validation**
   - File type checking
   - Size limits
   - Malware scanning (recommended)

2. **API Key Protection**
   - Environment variables
   - Never commit .env
   - Rate limiting

3. **User Authentication**
   - Django's built-in auth
   - Password hashing
   - Session management

4. **Input Sanitization**
   - XSS prevention
   - SQL injection protection
   - CSRF tokens

## Performance Optimization

1. **Caching**
   - Summary caching
   - Quiz result caching
   - Static file caching

2. **Database Optimization**
   - Indexed fields
   - Query optimization
   - Connection pooling

3. **AI API Optimization**
   - Request batching
   - Response caching
   - Fallback mechanisms

## Testing

**Run Tests:**
```bash
python manage.py test
```

**Test Coverage:**
- Unit tests for models
- Integration tests for views
- AI service mocking

## Deployment

### Development
```bash
python manage.py runserver
```

### Production (Gunicorn)
```bash
gunicorn studygenie.wsgi:application --bind 0.0.0.0:8000
```

### Environment Variables
```
GOOGLE_AI_API_KEY=your-key
DJANGO_SECRET_KEY=your-secret
DEBUG=False
ALLOWED_HOSTS=yourdomain.com
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

MIT License - see [LICENSE](LICENSE) file.
