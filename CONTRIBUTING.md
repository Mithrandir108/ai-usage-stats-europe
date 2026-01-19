# Contributing to AI Usage Statistics Dashboard

First off, thank you for considering contributing to this project! 🎉

## Code of Conduct

This project adheres to a simple principle: be respectful, constructive, and professional in all interactions.

## How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check existing issues. When creating a bug report, include:

- **Clear title** - Descriptive summary of the issue
- **Steps to reproduce** - How to trigger the bug
- **Expected behavior** - What should happen
- **Actual behavior** - What actually happens
- **Screenshots** - If applicable
- **Browser/OS** - Your environment details

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion:

- **Use a clear title** - Describe the enhancement
- **Detailed description** - Explain why this would be useful
- **Examples** - Show how it would work
- **Alternative solutions** - Consider other approaches

### Pull Requests

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Make your changes
4. Test thoroughly in multiple browsers
5. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
6. Push to the branch (`git push origin feature/AmazingFeature`)
7. Open a Pull Request

## Development Guidelines

### Code Style

**HTML**
- Use semantic HTML5 elements
- Maintain proper indentation (4 spaces)
- Include descriptive comments for complex sections
- Follow accessibility best practices

**CSS**
- Use consistent naming conventions
- Group related styles together
- Comment complex selectors
- Maintain mobile-first approach

**JavaScript**
- Use meaningful variable names
- Add comments for complex logic
- Follow ES6+ standards
- Ensure cross-browser compatibility

### Testing Checklist

Before submitting a PR, verify:

- [ ] Works in Chrome, Firefox, Safari
- [ ] Responsive on mobile devices
- [ ] No console errors
- [ ] All interactive features function correctly
- [ ] Data updates properly
- [ ] Charts render correctly
- [ ] Back navigation works
- [ ] Tooltips display properly

### Commit Message Guidelines

Use clear, descriptive commit messages:

```
feat: Add new country data visualization
fix: Correct back button navigation issue
docs: Update README with deployment instructions
style: Improve mobile responsive layout
refactor: Simplify country detail rendering
```

## Data Updates

### Adding New Countries

To add a new country to the dataset:

1. Add country code to `countryPositions` object with SVG coordinates
2. Add country data to `allData.countries` object:
```javascript
"NEW": {
    "name": "New Country",
    "usage_count": 12000,
    "soc_categories": [...],
    "top_tasks": [...],
    "collaboration": [...]
}
```

### Updating Existing Data

- Ensure data format consistency
- Update `last_updated` date
- Validate all numeric values
- Test chart rendering after changes

## Feature Requests Priority

**High Priority:**
- Additional country detailed data
- Performance improvements
- Accessibility enhancements
- Mobile UX improvements

**Medium Priority:**
- Additional chart types
- Export functionality
- Print-friendly view
- Dark mode support

**Low Priority:**
- Animation enhancements
- Easter eggs
- Experimental features

## Questions?

Feel free to:
- Open an issue for discussion
- Reach out via the contact information in README
- Check existing documentation

## Recognition

Contributors will be recognized in the README and project documentation.

Thank you for contributing! 🚀
