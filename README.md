# WORKFLOWCONTROL

A comprehensive HTML-based workflow control and project management tool for tracking Sales Orders (SO), purchase orders, documents, and project activities with AI-powered insights.

## Features

- **Dashboard**: Real-time KPI metrics and project overview
- **Project Management**: Create and track Sales Orders with detailed equipment specifications
- **Purchase Module**: Monitor equipment and capacity tracking
- **Document Management**: Centralized document control with revision tracking
- **Activity Logging**: Comprehensive audit trail for all project activities
- **AI Integration**: Claude API integration for workflow insights and analysis
- **Data Management**: Import/export functionality for data backup and migration
- **Theme Support**: Multiple color themes with dark mode support

## 🔒 Security

This application implements comprehensive security measures to protect against common web vulnerabilities.

### Security Features

#### 1. **Cross-Site Scripting (XSS) Protection**
- ✅ DOMPurify library integration for input sanitization
- ✅ Safe DOM manipulation methods
- ✅ HTML entity escaping for dynamic content
- ✅ Input validation and filtering

#### 2. **Content Security Policy (CSP)**
- ✅ Strict CSP headers via meta tags
- ✅ Restricted script sources
- ✅ Prevention of inline script execution
- ✅ Nonce-based CSP for necessary inline scripts

#### 3. **Security Headers**
- ✅ `X-Content-Type-Options: nosniff`
- ✅ `X-Frame-Options: SAMEORIGIN`
- ✅ `Referrer-Policy: strict-origin-when-cross-origin`
- ✅ `Permissions-Policy` for feature restrictions

#### 4. **Input Validation**
- ✅ Type validation for all inputs
- ✅ Length limits to prevent buffer overflow
- ✅ Format validation (email, phone, etc.)
- ✅ Special character sanitization

#### 5. **Data Protection**
- ✅ LocalStorage encryption recommendations
- ✅ Secure data handling practices
- ✅ Data minimization principles
- ✅ Export/import with validation

### Security Best Practices

#### For End Users

1. **Use HTTPS**: Always access the application over HTTPS
2. **Secure Device**: Ensure your device is malware-free and up-to-date
3. **Browser Security**: Use a modern, updated web browser
4. **Data Backup**: Regularly export your data for backup
5. **Clear Data**: Clear browser data when using shared devices

#### For Developers/Deployers

1. **HTTPS Only Deployment**
   ```bash
   # Deploy only to HTTPS-enabled hosting
   # GitHub Pages, Netlify, Vercel recommended
   ```

2. **Environment Variables for API Keys**
   ```javascript
   // Never commit API keys to version control
   // Use environment variables or backend proxy
   const API_KEY = process.env.CLAUDE_API_KEY; // Server-side only
   ```

3. **Server-Side Integration (Recommended)**
   For production environments, implement:
   - Backend API for sensitive operations
   - Server-side authentication (OAuth 2.0, JWT)
   - Database storage instead of localStorage
   - Server-side input validation
   - API rate limiting

4. **Regular Security Updates**
   ```bash
   # Check for dependency vulnerabilities
   npm audit
   
   # Update dependencies
   npm update
   ```

5. **Security Scanning**
   ```bash
   # Run CodeQL analysis (configured in GitHub Actions)
   # Check for XSS vulnerabilities
   # Review CSP compliance
   ```

### Known Security Limitations

⚠️ **Client-Side Only Architecture**: This is currently a client-side only application, which has inherent limitations:

- **No True Authentication**: Authentication is simulated; data is accessible in browser
- **LocalStorage Exposure**: Data stored locally is not encrypted by default
- **API Key Exposure**: Cannot securely store API keys in client-side code
- **Bypassable Validation**: Client-side validation can be circumvented

**Recommended for Production**: Implement a backend API with proper authentication, server-side validation, and database storage for sensitive data.

## Quick Start

### Option 1: Direct Browser Use

1. Clone or download the repository:
   ```bash
   git clone https://github.com/raikoushik/WORKFLOWCONTROL.git
   cd WORKFLOWCONTROL
   ```

2. Open `index.html` in a modern web browser:
   ```bash
   # On macOS
   open index.html
   
   # On Linux
   xdg-open index.html
   
   # On Windows
   start index.html
   ```

### Option 2: Local Web Server (Recommended)

For better security and testing, serve via a local web server:

```bash
# Using Python 3
python3 -m http.server 8000

# Using Node.js (http-server)
npx http-server -p 8000

# Using PHP
php -S localhost:8000
```

Then navigate to: `http://localhost:8000`

### Option 3: Deploy to GitHub Pages

1. Fork this repository
2. Go to Settings → Pages
3. Select branch: `main`, folder: `/ (root)`
4. Click Save
5. Access at: `https://[username].github.io/WORKFLOWCONTROL`

## Usage

### Project Management

1. **Create Project**: Click "+ New Project" in sidebar
2. **Fill Details**: SO Number, Client Name, Equipment, Capacity
3. **Track Progress**: Update milestones and status
4. **Add Notes**: Document important information

### Document Management

1. **Add Document**: Click "Add Document" button
2. **Enter Details**: Drawing Number, Description, Revision
3. **Track Revisions**: Update revision history
4. **Attach Notes**: Add commissioning reports and remarks

### Data Management

**Export Data**:
```
Settings → Export Data → Download JSON
```

**Import Data**:
```
Settings → Choose File → Import
```

⚠️ **Security Note**: Validate imported JSON files from trusted sources only

## AI Integration

To use AI features:

1. Obtain Claude API key from [Anthropic](https://www.anthropic.com/)
2. **⚠️ Security Warning**: For production, implement backend API proxy
3. Configure API key in application settings
4. Use AI insights for project analysis

**Recommended**: Never expose API keys in client-side code. Implement a backend proxy service.

## Browser Compatibility

- ✅ Chrome/Edge 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Opera 76+

Requires JavaScript enabled and localStorage support.

## Technology Stack

- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Storage**: localStorage (browser-based)
- **Security**: DOMPurify, CSP, Input Validation
- **AI**: Claude API (Anthropic)
- **Deployment**: Static hosting (GitHub Pages compatible)

## File Structure

```
WORKFLOWCONTROL/
├── index.html              # Main application file
├── ewc-master (6).html    # Alternative version
├── SECURITY.md            # Security policy and guidelines
├── README.md              # This file
└── .github/
    └── workflows/
        ├── deploy.yml     # GitHub Pages deployment
        └── security.yml   # Security scanning workflow
```

## Security Scanning

This repository includes automated security scanning:

- **CodeQL Analysis**: Automatic code scanning for vulnerabilities
- **Dependency Scanning**: Automated vulnerability detection
- **SAST Checks**: Static application security testing

View security alerts in: `Security` tab → `Code scanning alerts`

## Contributing

Contributions are welcome! Please follow these guidelines:

1. **Security First**: Review SECURITY.md before contributing
2. **Input Validation**: Always validate and sanitize user inputs
3. **Safe DOM Manipulation**: Use `textContent` instead of `innerHTML` when possible
4. **Test Security**: Run security scans before submitting PR
5. **Document Changes**: Update documentation for new features

### Development Workflow

```bash
# Fork and clone the repository
git clone https://github.com/[your-username]/WORKFLOWCONTROL.git

# Create a feature branch
git checkout -b feature/your-feature-name

# Make changes and test
# Run security checks

# Commit and push
git add .
git commit -m "Description of changes"
git push origin feature/your-feature-name

# Open Pull Request
```

## Reporting Security Issues

🔒 **Do NOT open public issues for security vulnerabilities**

Please report security issues privately:
1. Email repository owner directly
2. Include detailed description and reproduction steps
3. Allow time for fix before public disclosure

See SECURITY.md for full reporting guidelines.

## License

[Specify License Here]

## Support

- **Documentation**: See inline code comments
- **Security**: Review SECURITY.md
- **Issues**: Open GitHub issue (non-security)
- **Discussions**: Use GitHub Discussions for questions

## Roadmap

### Planned Security Enhancements
- [ ] Backend API implementation
- [ ] OAuth 2.0 authentication
- [ ] End-to-end encryption for data
- [ ] Server-side validation
- [ ] Rate limiting
- [ ] Advanced audit logging

### Feature Enhancements
- [ ] Multi-user support
- [ ] Real-time collaboration
- [ ] Advanced reporting
- [ ] Mobile app version
- [ ] Integration APIs

## Acknowledgments

- **DOMPurify**: For XSS protection
- **Anthropic**: For Claude AI integration
- **OWASP**: For security guidelines and best practices
- **GitHub**: For security scanning and hosting

## Changelog

### Version 2.0 (2026-02-19)
- ✅ Added comprehensive security measures
- ✅ Implemented DOMPurify for XSS protection
- ✅ Added Content Security Policy
- ✅ Implemented input validation framework
- ✅ Added security headers
- ✅ Created security documentation
- ✅ Added automated security scanning

### Version 1.0
- Initial release
- Basic project management features
- Document tracking
- AI integration

---

**⚠️ Important**: This application is designed for educational and small-scale use. For production environments handling sensitive data, implement proper backend infrastructure with authentication, authorization, and server-side validation.

**Built with security in mind** 🔒 | **Last Updated**: 2026-02-19
