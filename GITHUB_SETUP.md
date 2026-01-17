# GitHub Repository Setup Guide

Step-by-step guide to upload StudyGenie to GitHub.

## Prerequisites
- Git installed on your system
- GitHub account created
- Project files ready

## Step 1: Initialize Git Repository

Open terminal/command prompt in your project directory:

```bash
cd c:\Users\adity\OneDrive\Desktop\ha\sunhacks\studygenie

# Initialize git repository
git init

# Add all files
git add .

# Create first commit
git commit -m "Initial commit: StudyGenie v1.0"
```

## Step 2: Create GitHub Repository

1. Go to https://github.com
2. Click the "+" icon → "New repository"
3. Fill in details:
   - **Repository name**: `studygenie`
   - **Description**: "AI-Powered Study Companion - Transform documents into interactive study materials"
   - **Visibility**: Public (or Private)
   - **DO NOT** initialize with README, .gitignore, or license (we already have these)
4. Click "Create repository"

## Step 3: Connect Local to GitHub

Copy the commands from GitHub (they'll look like this):

```bash
# Add remote repository
git remote add origin https://github.com/YOUR_USERNAME/studygenie.git

# Rename branch to main (if needed)
git branch -M main

# Push to GitHub
git push -u origin main
```

## Step 4: Verify Upload

1. Refresh your GitHub repository page
2. You should see all files uploaded
3. README.md will be displayed automatically

## Step 5: Configure Repository Settings

### Add Topics
Go to repository → About (gear icon) → Add topics:
- `django`
- `python`
- `ai`
- `education`
- `study-tool`
- `machine-learning`
- `gemini-ai`
- `quiz-generator`

### Add Description
"🧞♂️ AI-Powered Study Companion - Transform PDFs into summaries, quizzes, and flashcards using Google Gemini AI"

### Add Website (if deployed)
Add your deployment URL

### Enable Features
- ✅ Issues
- ✅ Projects
- ✅ Wiki (optional)
- ✅ Discussions (optional)

## Step 6: Protect Sensitive Files

Verify `.gitignore` is working:

```bash
# Check what's being tracked
git status

# These should NOT appear:
# - .env (your actual environment file)
# - db.sqlite3 (database)
# - media/documents/* (uploaded files)
# - __pycache__/ (Python cache)
```

## Step 7: Create Releases

1. Go to repository → Releases → "Create a new release"
2. Tag version: `v1.0.0`
3. Release title: `StudyGenie v1.0.0 - Initial Release`
4. Description: Copy from CHANGELOG.md
5. Click "Publish release"

## Common Git Commands

```bash
# Check status
git status

# Add specific files
git add filename.py

# Add all changes
git add .

# Commit changes
git commit -m "Description of changes"

# Push to GitHub
git push

# Pull latest changes
git pull

# Create new branch
git checkout -b feature-name

# Switch branches
git checkout main

# View commit history
git log
```

## Troubleshooting

### "Permission denied" Error
Use HTTPS or setup SSH keys:
```bash
# HTTPS (will ask for username/password)
git remote set-url origin https://github.com/YOUR_USERNAME/studygenie.git

# Or use Personal Access Token
# GitHub Settings → Developer settings → Personal access tokens
```

### ".env file is tracked"
If you accidentally committed .env:
```bash
# Remove from git (keeps local file)
git rm --cached .env

# Commit the removal
git commit -m "Remove .env from tracking"

# Push changes
git push
```

### Large files error
GitHub has 100MB file limit. If you have large files:
```bash
# Use Git LFS for large files
git lfs install
git lfs track "*.pdf"
git add .gitattributes
```

## Best Practices

1. **Never commit**:
   - API keys
   - Passwords
   - Database files
   - User uploads

2. **Always commit**:
   - Source code
   - Documentation
   - Configuration templates (.env.example)
   - Requirements files

3. **Commit messages**:
   - Use clear, descriptive messages
   - Start with verb: "Add", "Fix", "Update", "Remove"
   - Example: "Add flashcard review feature"

4. **Branch strategy**:
   - `main` - stable production code
   - `develop` - development branch
   - `feature/*` - new features
   - `bugfix/*` - bug fixes

## Next Steps

After uploading to GitHub:

1. ✅ Add repository badges to README
2. ✅ Setup GitHub Actions (already configured)
3. ✅ Enable GitHub Pages (for documentation)
4. ✅ Add collaborators (if team project)
5. ✅ Star your own repository 😊
6. ✅ Share with community

## Repository URL Format

Your repository will be available at:
```
https://github.com/YOUR_USERNAME/studygenie
```

Clone URL:
```
https://github.com/YOUR_USERNAME/studygenie.git
```

## Updating Repository

When you make changes:

```bash
# 1. Check what changed
git status

# 2. Add changes
git add .

# 3. Commit with message
git commit -m "Update: description of changes"

# 4. Push to GitHub
git push
```

## Getting Help

- Git documentation: https://git-scm.com/doc
- GitHub guides: https://guides.github.com
- GitHub support: https://support.github.com

---

🎉 Congratulations! Your project is now on GitHub!
