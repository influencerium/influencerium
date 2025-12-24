# Contributing to Influencerium

Thank you for your interest in contributing to Influencerium! We welcome contributions from everyone.

## Code of Conduct

Please be respectful and constructive in all interactions. We're committed to providing a welcoming and inclusive environment for all contributors.

## How to Contribute

### Reporting Bugs

1. Check if the bug has already been reported in [Issues](https://github.com/yourusername/influencerium/issues)
2. If not, create a new issue with:
   - Clear title describing the bug
   - Detailed description of the issue
   - Steps to reproduce
   - Expected vs actual behavior
   - Screenshots/logs if applicable
   - Your environment (OS, browser, Node version, etc.)

### Suggesting Features

1. Check if the feature has been suggested in [Issues](https://github.com/yourusername/influencerium/issues)
2. If not, create a new issue with:
   - Clear title describing the feature
   - Detailed description of the feature
   - Use cases and benefits
   - Possible implementation approach
   - Any relevant mockups or examples

### Submitting Pull Requests

1. **Fork the repository**
   ```bash
   git clone https://github.com/yourusername/influencerium.git
   cd influencerium
   ```

2. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make your changes**
   - Follow the code style guidelines
   - Write clear, descriptive commit messages
   - Add tests for new functionality
   - Update documentation as needed

4. **Commit your changes**
   ```bash
   git commit -m "feat: add your feature description"
   ```

5. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

6. **Create a Pull Request**
   - Provide a clear title and description
   - Reference any related issues
   - Ensure all tests pass
   - Request review from maintainers

## Development Guidelines

### Code Style

- Use TypeScript for type safety
- Follow ESLint configuration
- Use Prettier for code formatting
- Write meaningful variable and function names
- Add comments for complex logic

### Commit Messages

Follow conventional commits format:
```
type(scope): subject

body

footer
```

Types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

Example:
```
feat(auth): add Google OAuth integration

- Implement Google OAuth 2.0 flow
- Add user profile mapping
- Update authentication service

Closes #123
```

### Testing

- Write unit tests for new features
- Maintain 80%+ code coverage
- Run tests before submitting PR
- Include integration tests for API endpoints

```bash
npm run test
npm run test:coverage
```

### Documentation

- Update README.md for user-facing changes
- Update API documentation for endpoint changes
- Add JSDoc comments for functions
- Update ROADMAP.md for feature additions

## Development Setup

See [Getting Started](./docs/GETTING_STARTED.md) for detailed setup instructions.

Quick start:
```bash
npm install
cp .env.example .env.local
docker-compose up -d
npm run db:migrate
npm run dev
```

## Review Process

1. **Automated Checks**
   - GitHub Actions runs tests and linting
   - Code coverage must be maintained
   - All checks must pass

2. **Code Review**
   - At least 2 approvals required
   - Maintainers will review for:
     - Code quality
     - Test coverage
     - Documentation
     - Performance impact
     - Security considerations

3. **Merge**
   - Squash commits for cleaner history
   - Delete feature branch after merge
   - Update related issues

## Questions?

- 📧 Email: support@influencerium.com
- 💬 Discord: [Join Community](https://discord.gg/influencerium)
- 📖 Docs: [Full Documentation](https://docs.influencerium.com)

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing to Influencerium! 🚀
