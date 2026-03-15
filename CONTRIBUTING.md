# Contributing to WorkflowGuard

Thank you for considering contributing to WorkflowGuard! 🛡️

## How to Contribute

### 🐛 Report Bugs

Found a bug? [Open an issue](https://github.com/pisanodesigner/workflowguard/issues/new) with:
- Description of the bug
- Steps to reproduce
- Expected vs actual behavior
- Sample workflow JSON (sanitized, no real credentials!)
- Browser/OS information

### 💡 Suggest Features

Have an idea? [Start a discussion](https://github.com/pisanodesigner/workflowguard/discussions/new) describing:
- The problem you're trying to solve
- Your proposed solution
- Why this would be valuable

### 🔍 Add Detection Patterns

The most valuable contributions are new security patterns!

**Example: Adding a new credential pattern**

1. Fork the repository
2. Open `workflowguard-poc.html`
3. Find the `PATTERNS` object (around line 253)
4. Add your pattern following this format:

```javascript
newCredentialType: {
    regex: /your-regex-pattern/g,
    severity: 'critical', // or 'high', 'medium'
    title: 'Credential Type Detected',
    description: 'Why this is a security risk.',
    remediation: 'How to fix it properly.'
}
```

5. Test it with a sample workflow
6. Submit a pull request

**Patterns we'd love to see:**
- MongoDB connection strings
- PostgreSQL/MySQL credentials
- SendGrid API keys
- Twilio auth tokens
- Firebase keys
- Azure credentials
- Google Cloud credentials
- API keys from popular services (Mailchimp, HubSpot, etc.)

### 🎨 Improve UI/UX

Design improvements are welcome! Please:
- Maintain the existing color scheme (teal #3e8c9c)
- Keep it accessible (WCAG AA compliant)
- Ensure mobile responsiveness
- Test in Chrome, Firefox, Safari

### 📝 Documentation

Help improve the README, add examples, write tutorials!

## Pull Request Process

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-pattern`)
3. **Commit** your changes (`git commit -m 'Add detection for X credential'`)
4. **Push** to your branch (`git push origin feature/amazing-pattern`)
5. **Open** a Pull Request

### PR Guidelines

- ✅ Clear title and description
- ✅ Reference any related issues
- ✅ Test your changes thoroughly
- ✅ Keep changes focused (one feature per PR)
- ✅ Update README if needed

## Code Style

**JavaScript:**
- Use clear, descriptive variable names
- Add comments for complex regex patterns
- Follow existing code formatting
- No external dependencies (keep it pure JS)

**HTML/CSS:**
- Clean, semantic HTML
- CSS follows existing convention
- Mobile-first responsive design

## Testing

Before submitting:
1. Test with real workflow JSON files (sanitized)
2. Verify patterns don't have false positives
3. Check it works in Chrome, Firefox, Safari
4. Test on mobile devices

## Community Guidelines

- Be respectful and constructive
- Help others learn
- Focus on the problem, not the person
- Security researchers: Please disclose vulnerabilities responsibly

## Questions?

Not sure about something? 
- [Open a discussion](https://github.com/pisanodesigner/workflowguard/discussions)
- Check existing issues and PRs
- Contact: [pisanodesigner.com/contact](mailto:radu@pisanodesigner.com)

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

**Thank you for helping make automation workflows more secure! 🙏**
