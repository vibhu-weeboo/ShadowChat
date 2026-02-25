# Contributing to ShadowChat

First off, thank you for considering contributing to ShadowChat! It's people like you that make ShadowChat such a great tool.

## Code of Conduct

This project and everyone participating in it is governed by our Code of Conduct. By participating, you are expected to uphold this code.

## How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check the issue list as you might find out that you don't need to create one. When you are creating a bug report, please include as many details as possible:

- **Use a clear and descriptive title**
- **Describe the exact steps which reproduce the problem** in as many details as possible
- **Provide specific examples** to demonstrate the steps
- **Describe the behavior you observed** after following the steps
- **Explain which behavior you expected** to see instead and why
- **Include screenshots and animated GIFs** if possible
- **Include your environment** (OS, browser, Node version, etc.)

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, please include:

- **Use a clear and descriptive title** for the issue
- **Provide a step-by-step description** of the suggested enhancement
- **Provide specific examples** to demonstrate the steps
- **Describe the current behavior** and **explain the expected behavior**
- **Explain why this enhancement would be useful**

### Pull Requests

- Fill in the required template
- Follow the JavaScript/React styleguides
- Include appropriate test cases
- Update documentation as needed
- End all files with a newline

## Styleguides

### Git Commit Messages

- Use the present tense ("Add feature" not "Added feature")
- Use the imperative mood ("Move cursor to..." not "Moves cursor to...")
- Limit the first line to 72 characters or less
- Reference issues and pull requests liberally after the first line
- Follow Conventional Commits format:

```
feat: Add new feature
fix: Fix bug
docs: Update documentation
style: Code style changes
refactor: Code refactoring
test: Add/update tests
chore: Maintenance tasks
perf: Performance improvements
```

### JavaScript/React Styleguide

- Use 2 spaces for indentation
- Use `const` by default, `let` if you need to reassign
- Prefer template literals over string concatenation
- Use arrow functions when appropriate
- Use meaningful variable names
- Add comments for complex logic

```javascript
// Good
const calculateHash = (data) => {
  return nacl.hash(nacl.util.decodeBase64(data));
};

// Bad
const calc = (d) => nacl.hash(nacl.util.decodeBase64(d));
```

### React Component Styleguide

- Use functional components with hooks
- Keep components small and focused
- Use meaningful prop names
- Add PropTypes for type checking
- Use descriptive state variable names

```javascript
const MessageInput = ({ onSendMessage }) => {
  const [message, setMessage] = useState('');
  
  const handleSubmit = (e) => {
    e.preventDefault();
    if (message.trim()) {
      onSendMessage(message);
      setMessage('');
    }
  };
  
  return (
    <form onSubmit={handleSubmit}>
      <input
        type="text"
        value={message}
        onChange={(e) => setMessage(e.target.value)}
        placeholder="Type a message..."
      />
      <button type="submit">Send</button>
    </form>
  );
};
```

## Development Setup

### Prerequisites
- Node.js 18.0+
- npm or yarn
- MongoDB (local or Atlas)
- Git

### Installation

1. Fork the repo
2. Clone your fork:
   ```bash
   git clone https://github.com/your-username/ShadowChat.git
   cd ShadowChat
   ```

3. Install dependencies:
   ```bash
   npm install
   ```

4. Create a `.env` file:
   ```bash
   cp .env.example .env
   ```

5. Update `.env` with your local configuration

6. Start development servers:
   ```bash
   npm run dev
   ```

### Testing

```bash
# Run all tests
npm test

# Run tests in watch mode
npm test -- --watch

# Generate coverage report
npm test -- --coverage
```

### Linting

```bash
# Check for linting errors
npm run lint

# Fix linting errors
npm run lint -- --fix

# Format code with Prettier
npm run format
```

## Pull Request Process

1. Update the README.md with details of changes if applicable
2. Update the version number in package.json following SemVer
3. Ensure all tests pass and coverage is maintained
4. Run `npm run lint` and fix any issues
5. Create a descriptive pull request

## Additional Notes

### Issue and Pull Request Labels

This section lists the labels we use to help organize and categorize issues and pull requests.

- `bug` - Something isn't working
- `enhancement` - New feature or request
- `documentation` - Improvements or additions to documentation
- `good first issue` - Good for newcomers
- `help wanted` - Extra attention is needed
- `question` - Further information is requested
- `security` - Security-related issues

## Recognition

Contributors will be recognized in:
- The README.md file
- Release notes
- GitHub contributors page

## Questions?

Feel free to open an issue with the label `question` or reach out to us on Discord.

Thank you for contributing to ShadowChat! 🎉
