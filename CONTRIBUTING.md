# Contributing to Calculus Calculator

First off, thank you for considering contributing to Calculus Calculator! It's people like you that make this project such a great tool for the mathematics community.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Getting Started](#getting-started)
- [Development Process](#development-process)
- [Style Guidelines](#style-guidelines)
- [Commit Guidelines](#commit-guidelines)
- [Pull Request Process](#pull-request-process)
- [Testing Guidelines](#testing-guidelines)

## Code of Conduct

### Our Pledge

We pledge to make participation in our project a harassment-free experience for everyone, regardless of age, body size, disability, ethnicity, gender identity and expression, level of experience, nationality, personal appearance, race, religion, or sexual identity and orientation.

### Our Standards

**Examples of behavior that contributes to a positive environment:**
- Using welcoming and inclusive language
- Being respectful of differing viewpoints and experiences
- Gracefully accepting constructive criticism
- Focusing on what is best for the community
- Showing empathy towards other community members

**Examples of unacceptable behavior:**
- The use of sexualized language or imagery
- Trolling, insulting/derogatory comments, and personal attacks
- Public or private harassment
- Publishing others' private information without permission
- Other conduct which could reasonably be considered inappropriate

## How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check the existing issues to avoid duplicates. When creating a bug report, include as many details as possible:

**Bug Report Template:**
```markdown
**Description:**
A clear description of the bug.

**Steps to Reproduce:**
1. Step one
2. Step two
3. Step three

**Expected Behavior:**
What you expected to happen.

**Actual Behavior:**
What actually happened.

**Environment:**
- OS: [e.g., Windows 10, macOS 12, Ubuntu 22.04]
- Python Version: [e.g., 3.10.5]
- Calculator Version: [e.g., 1.0.0]

**Additional Context:**
Any other relevant information.
```

### Suggesting Features

Feature requests are welcome! Please provide:

- **Clear description** of the feature
- **Use cases** explaining why it's needed
- **Examples** of how it would work
- **Alternatives** you've considered

### Contributing Code

We love code contributions! Here's how to get started:

## Getting Started

### 1. Fork and Clone

```bash
# Fork the repository on GitHub
# Then clone your fork
git clone https://github.com/YOUR_USERNAME/Calculus-Calculator.git
cd Calculus-Calculator
```

### 2. Set Up Development Environment

```bash
# Create a virtual environment (recommended)
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Install development dependencies
pip install pytest pytest-cov flake8 black mypy
```

### 3. Create a Branch

```bash
# Create a new branch for your feature or bugfix
git checkout -b feature/your-feature-name
# or
git checkout -b bugfix/issue-number-description
```

## Development Process

### 1. Make Your Changes

- Write clean, readable code
- Follow the existing code style
- Add comments for complex logic
- Update documentation as needed

### 2. Write Tests

All new features must include tests:

```python
# tests/test_your_feature.py
import pytest
from calculator import CalculusCalculator

def test_your_feature():
    """Test description."""
    calc = CalculusCalculator()
    result = calc.calculate("your_expression")
    assert result['success'] == True
    assert result['result'] == "expected_output"

def test_your_feature_edge_case():
    """Test edge case."""
    calc = CalculusCalculator()
    result = calc.calculate("edge_case_expression")
    assert result['success'] == False
    assert "error" in result
```

### 3. Run Tests

```bash
# Run all tests
python -m pytest tests/ -v

# Run with coverage
python -m pytest tests/ --cov=. --cov-report=html

# Run specific test file
python -m pytest tests/test_your_feature.py
```

### 4. Check Code Quality

```bash
# Format code with Black
black .

# Check style with flake8
flake8 . --max-line-length=100

# Type checking with mypy
mypy calculator.py
```

## Style Guidelines

### Python Style Guide

We follow **PEP 8** with some modifications:

- **Line length**: Maximum 100 characters (not 79)
- **Indentation**: 4 spaces (no tabs)
- **Quotes**: Prefer double quotes for strings
- **Imports**: Organized in three groups (standard library, third-party, local)

### Code Structure

```python
"""
Module docstring describing the module's purpose.
"""

import standard_library
import third_party
from local_module import something


class MyClass:
    """Class docstring."""

    def __init__(self):
        """Initialize the class."""
        self.attribute = None

    def my_method(self, param: str) -> bool:
        """
        Method docstring.

        Args:
            param (str): Parameter description

        Returns:
            bool: Return value description
        """
        return True


def my_function(arg1: int, arg2: str) -> str:
    """
    Function docstring.

    Args:
        arg1 (int): First argument
        arg2 (str): Second argument

    Returns:
        str: Return value
    """
    return f"{arg1}: {arg2}"
```

### Documentation Style

- **Docstrings**: Use Google-style docstrings
- **Comments**: Explain *why*, not *what*
- **Type hints**: Use type annotations for function parameters and returns
- **README**: Update if adding features or changing behavior

## Commit Guidelines

### Commit Message Format

Use conventional commit messages:

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

**Examples:**
```
feat(derivatives): Add support for hyperbolic functions

Implement sinh, cosh, and tanh derivatives with corresponding
tests and documentation updates.

Closes #123
```

```
fix(parser): Handle empty expressions correctly

Previously, empty expressions would cause a crash. Now they
return a proper error message.

Fixes #456
```

### Commit Best Practices

- **Atomic commits**: One logical change per commit
- **Clear messages**: Explain what and why
- **Test before commit**: Ensure tests pass
- **Sign commits**: Use `git commit -s` for sign-off

## Pull Request Process

### Before Submitting

- [ ] Code follows style guidelines
- [ ] Tests added for new features
- [ ] All tests pass
- [ ] Documentation updated
- [ ] Commit messages follow guidelines
- [ ] Branch is up to date with main

### Submitting Pull Request

1. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

2. **Create Pull Request**
   - Go to the original repository
   - Click "New Pull Request"
   - Select your branch
   - Fill in the PR template

3. **PR Description Template**
   ```markdown
   ## Description
   Brief description of changes

   ## Type of Change
   - [ ] Bug fix
   - [ ] New feature
   - [ ] Breaking change
   - [ ] Documentation update

   ## Testing
   - [ ] Tests added/updated
   - [ ] All tests pass
   - [ ] Manual testing completed

   ## Checklist
   - [ ] Code follows style guidelines
   - [ ] Documentation updated
   - [ ] No new warnings
   - [ ] Commit messages follow guidelines

   ## Related Issues
   Closes #123
   ```

### After Submission

- **Respond to feedback**: Address review comments promptly
- **Update PR**: Push additional commits as needed
- **Be patient**: Maintainers will review when available
- **Stay engaged**: Participate in discussions

## Testing Guidelines

### Test Structure

```python
# tests/test_module.py
import pytest
from your_module import YourClass


class TestYourClass:
    """Test suite for YourClass."""

    @pytest.fixture
    def instance(self):
        """Create instance for testing."""
        return YourClass()

    def test_basic_functionality(self, instance):
        """Test basic functionality."""
        result = instance.method()
        assert result == expected_value

    def test_edge_case(self, instance):
        """Test edge case."""
        with pytest.raises(ValueError):
            instance.method(invalid_input)

    @pytest.mark.parametrize("input,expected", [
        (1, 2),
        (2, 4),
        (3, 6),
    ])
    def test_multiple_inputs(self, instance, input, expected):
        """Test with multiple inputs."""
        result = instance.method(input)
        assert result == expected
```

### Test Coverage

- **Minimum coverage**: 80%
- **Critical code**: 100% coverage for core functionality
- **Edge cases**: Test boundary conditions
- **Error handling**: Test error scenarios

### Running Tests

```bash
# Run all tests with coverage
python -m pytest tests/ --cov=. --cov-report=html --cov-report=term

# View coverage report
open htmlcov/index.html  # macOS
xdg-open htmlcov/index.html  # Linux
start htmlcov/index.html  # Windows
```

## Questions?

If you have questions about contributing:

1. **Check Documentation**: Review README and inline comments
2. **Search Issues**: Look for similar questions
3. **Ask in Discussions**: Start a discussion on GitHub
4. **Contact Maintainers**: Reach out directly if needed

## Recognition

Contributors will be:
- Listed in CONTRIBUTORS.md
- Mentioned in release notes
- Credited in commit messages
- Appreciated by the community!

## Thank You!

Your contributions make this project better for everyone. Thank you for being part of the Calculus Calculator community!

---

*Happy coding! 🧮✨*
