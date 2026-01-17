# Security Policy

## Supported Versions

Currently supported versions of StudyGenie:

| Version | Supported          |
| ------- | ------------------ |
| 1.0.x   | :white_check_mark: |

## Reporting a Vulnerability

We take the security of StudyGenie seriously. If you discover a security vulnerability, please follow these steps:

1. **Do Not** open a public issue
2. Email the details to the project maintainers (create a private security advisory on GitHub)
3. Include:
   - Description of the vulnerability
   - Steps to reproduce
   - Potential impact
   - Suggested fix (if any)

## Security Best Practices

When deploying StudyGenie:

1. **Never commit** your `.env` file with real API keys
2. **Change** the Django `SECRET_KEY` in production
3. **Set** `DEBUG = False` in production
4. **Use** HTTPS in production environments
5. **Regularly update** dependencies
6. **Restrict** file upload types and sizes
7. **Validate** all user inputs
8. **Use** environment variables for sensitive data

## Response Timeline

- We will acknowledge receipt within 48 hours
- We will provide a detailed response within 7 days
- We will work on a fix and keep you updated

Thank you for helping keep StudyGenie secure!
