# Contributing to Revive Peace

Thank you for your interest in contributing to Revive Peace! This document provides guidelines and information for contributors.

## 🤝 How to Contribute

### Reporting Issues
- Use the [GitHub Issues](https://github.com/yourusername/revive-peace/issues) page
- Search existing issues before creating a new one
- Provide detailed information including:
  - Browser and version
  - Steps to reproduce
  - Expected vs actual behavior
  - Screenshots if applicable

### Suggesting Features
- Open a [GitHub Discussion](https://github.com/yourusername/revive-peace/discussions)
- Describe the feature and its benefits
- Consider the mental wellness focus of the application

### Code Contributions

#### Getting Started
1. Fork the repository
2. Clone your fork locally
3. Create a new branch for your feature/fix
4. Make your changes
5. Test thoroughly
6. Submit a pull request

#### Development Setup
```bash
git clone https://github.com/yourusername/revive-peace.git
cd revive-peace
# Open html/main.html in your browser or use a local server
python -m http.server 8000
```

#### Branch Naming Convention
- `feature/feature-name` - New features
- `fix/bug-description` - Bug fixes
- `docs/update-description` - Documentation updates
- `style/improvement-description` - UI/UX improvements

## 📋 Development Guidelines

### Code Style
- **HTML**: Use semantic HTML5 elements
- **CSS**: Follow BEM methodology where possible
- **JavaScript**: Use ES6+ features, avoid jQuery for new code
- **Indentation**: 2 spaces for HTML/CSS, 2 spaces for JavaScript
- **Comments**: Add comments for complex logic

### File Organization
```
html/           # All HTML pages
css/            # Stylesheets (organized by feature)
js/             # JavaScript files
images/         # Image assets
plugins/        # Third-party libraries
```

### Testing Checklist
- [ ] Test on Chrome, Firefox, Safari, Edge
- [ ] Test on mobile devices (responsive design)
- [ ] Verify accessibility (keyboard navigation, screen readers)
- [ ] Check console for errors
- [ ] Validate HTML and CSS
- [ ] Test all interactive features

### Accessibility Requirements
- Use semantic HTML elements
- Provide alt text for images
- Ensure keyboard navigation works
- Maintain color contrast ratios (WCAG AA)
- Add ARIA labels where needed

## 🎯 Areas for Contribution

### High Priority
- **Mobile Optimization**: Improve mobile user experience
- **Accessibility**: Enhance screen reader compatibility
- **Performance**: Optimize loading times and animations
- **Browser Compatibility**: Fix cross-browser issues

### Medium Priority
- **New Games**: Add therapeutic games following existing patterns
- **UI/UX Improvements**: Enhance visual design and user flow
- **Content**: Add more wellness resources and content
- **Internationalization**: Add support for multiple languages

### Low Priority
- **Advanced Features**: User accounts, cloud sync
- **Analytics**: Usage tracking and insights
- **PWA Features**: Offline support, app-like experience

## 🧪 Adding New Features

### New Therapeutic Games
1. Create HTML file in `html/` directory
2. Create corresponding CSS file in `css/`
3. Follow existing game structure and patterns
4. Include progress tracking and statistics
5. Add to navigation menus
6. Update dashboard integration

### New Wellness Tools
1. Research therapeutic benefits
2. Design user-friendly interface
3. Implement with accessibility in mind
4. Add to appropriate navigation sections
5. Include usage instructions

## 📝 Pull Request Process

### Before Submitting
- [ ] Code follows project style guidelines
- [ ] All tests pass (manual testing)
- [ ] Documentation updated if needed
- [ ] Commit messages are clear and descriptive

### PR Description Template
```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Style/UI improvement

## Testing
- [ ] Tested on multiple browsers
- [ ] Tested on mobile devices
- [ ] Verified accessibility

## Screenshots (if applicable)
Add screenshots of UI changes

## Additional Notes
Any additional information or context
```

### Review Process
1. Automated checks (if any)
2. Code review by maintainers
3. Testing by reviewers
4. Approval and merge

## 🌟 Recognition

Contributors will be recognized in:
- README.md contributors section
- Release notes for significant contributions
- Special thanks in documentation

## 📞 Getting Help

- **Questions**: Use [GitHub Discussions](https://github.com/yourusername/revive-peace/discussions)
- **Real-time Chat**: Join our community Discord (link in README)
- **Email**: Contact maintainers at contribute@revivepeace.com

## 🎨 Design Guidelines

### Color Palette
- Primary: #007bff (Blue)
- Secondary: #6c757d (Gray)
- Success: #28a745 (Green)
- Warning: #ffc107 (Yellow)
- Danger: #dc3545 (Red)

### Typography
- Primary Font: 'Nunito', sans-serif
- Headings: Bold weights (600-700)
- Body: Regular weight (400)

### UI Principles
- **Calming**: Use soft colors and gentle animations
- **Accessible**: High contrast, clear navigation
- **Responsive**: Mobile-first design approach
- **Intuitive**: Clear visual hierarchy and user flow

## 🔒 Security Considerations

- No sensitive data storage (everything is local)
- Validate all user inputs
- Use HTTPS for external resources
- Follow OWASP guidelines for web security

## 📄 License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for helping make mental wellness more accessible through technology! 🌟