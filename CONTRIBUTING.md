# Contributing to FAEAP

Thank you for your interest in contributing to the Forensic Audio Evidence Authentication Platform (FAEAP). This document provides guidelines for contributing to the project.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [Contributing Guidelines](#contributing-guidelines)
- [Pull Request Process](#pull-request-process)
- [Coding Standards](#coding-standards)
- [Documentation](#documentation)
- [Testing](#testing)
- [Reporting Issues](#reporting-issues)

## Code of Conduct

### Our Pledge

We are committed to providing a welcoming and inclusive environment for all contributors. We pledge to:

- Be respectful and considerate
- Use inclusive language
- Be open to different viewpoints
- Focus on constructive feedback
- Gracefully accept constructive criticism

### Our Standards

Examples of behavior that contributes to a positive environment:

- Using welcoming and inclusive language
- Being respectful of differing opinions and viewpoints
- Gracefully accepting constructive criticism
- Focusing on what is best for the community
- Showing empathy towards other community members

Examples of unacceptable behavior:

- The use of sexualized language or imagery
- Trolling, insulting or derogatory comments
- Personal or political attacks
- Public or private harassment
- Publishing others' private information

### Reporting Issues

If you witness or experience unacceptable behavior, please contact the project maintainers.

## Getting Started

### Prerequisites

- Python 3.10 or higher
- Node.js 18 or higher
- Git
- Docker (optional, for containerized development)

### Clone the Repository

```bash
git clone https://github.com/yourusername/FAEAP.git
cd FAEAP
```

### Install Dependencies

#### Backend Dependencies

```bash
cd backend
pip install -r ../requirements.txt
```

#### Frontend Dependencies

```bash
cd frontend
npm install
```

## Development Setup

### Backend Setup

1. **Environment Variables**

Create a `.env` file in the backend directory:

```bash
DATABASE_URL=postgresql://user:password@localhost:5432/faeap
REDIS_URL=redis://localhost:6379/0
MINIO_ENDPOINT=localhost:9000
MINIO_ACCESS_KEY=minioadmin
MINIO_SECRET_KEY=minioadmin
SECRET_KEY=your-secret-key
```

2. **Database Setup**

```bash
# Run migrations
alembic upgrade head

# Create database
python scripts/create_database.py
```

3. **Run Development Server**

```bash
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

### Frontend Setup

1. **Environment Variables**

Create a `.env.local` file in the frontend directory:

```bash
NEXT_PUBLIC_API_URL=http://localhost:8000
```

2. **Run Development Server**

```bash
npm run dev
```

## Contributing Guidelines

### Types of Contributions

We welcome the following types of contributions:

- Bug fixes
- New features
- Documentation improvements
- Performance improvements
- Test additions
- Code refactoring

### Before You Contribute

1. **Check Existing Issues**

Search existing issues to avoid duplicates.

2. **Discuss Major Changes**

For major changes or new features, open an issue first to discuss the proposed changes.

3. **Follow Coding Standards**

Adhere to the coding standards outlined in this document.

4. **Write Tests**

Include tests for new functionality.

5. **Update Documentation**

Update relevant documentation for your changes.

### Small Changes

For small changes (typos, bug fixes, minor improvements):

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

### Large Changes

For large changes (new features, refactoring):

1. Open an issue to discuss the proposed changes
2. Get approval from maintainers
3. Follow the process for small changes

## Pull Request Process

### Branch Naming

Use descriptive branch names:

- `feature/description` for new features
- `bugfix/description` for bug fixes
- `hotfix/description` for urgent fixes
- `refactor/description` for refactoring

### Commit Messages

Follow conventional commit format:

```
<type>(<scope>): <subject>

<body>

<footer>
```

Types:
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes
- `refactor`: Code refactoring
- `test`: Test changes
- `chore`: Build process or auxiliary tool changes

Example:
```
feat(backend): add audio upload endpoint

Implement POST /api/v1/audio/upload endpoint with file validation,
hash calculation, and MinIO storage.

Closes #123
```

### Pull Request Template

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Testing
- [ ] Unit tests added/updated
- [ ] Integration tests added/updated
- [ ] Manual testing completed

## Checklist
- [ ] Code follows project style guidelines
- [ ] Self-review completed
- [ ] Commented complex code
- [ ] Updated documentation
- [ ] No new warnings generated
- [ ] Added/updated tests
- [ ] All tests passing

## Related Issues
Closes #123, #456
```

### Review Process

1. Automated checks must pass (linting, tests)
2. At least one maintainer approval required
3. Address all review comments
4. Squash commits if requested
5. Merge when approved

## Coding Standards

### Python (Backend)

#### Style Guide

- Follow PEP 8
- Use Black for formatting
- Maximum line length: 100 characters
- Use type hints for function signatures

#### Naming Conventions

- Variables/Functions: `snake_case`
- Classes: `PascalCase`
- Constants: `UPPER_SNAKE_CASE`
- Private members: `_leading_underscore`

#### Example

```python
from typing import List, Optional
import numpy as np

class AudioProcessor:
    """Processes audio files for forensic analysis."""
    
    MAX_SAMPLE_RATE = 48000
    
    def __init__(self, sample_rate: int = 16000):
        """Initialize audio processor."""
        self.sample_rate = sample_rate
        self._audio_data: Optional[np.ndarray] = None
    
    def load_audio(self, file_path: str) -> np.ndarray:
        """Load audio file."""
        # Implementation
        pass
```

### TypeScript/React (Frontend)

#### Style Guide

- Follow ESLint rules
- Use Prettier for formatting
- Maximum line length: 100 characters
- Use TypeScript strict mode

#### Naming Conventions

- Components: `PascalCase`
- Functions/Variables: `camelCase`
- Constants: `UPPER_SNAKE_CASE`
- Types/Interfaces: `PascalCase`

#### Example

```typescript
interface AudioFile {
  id: string;
  name: string;
  duration: number;
}

const MAX_FILE_SIZE = 500 * 1024 * 1024;

function validateAudioFile(file: File): boolean {
  return file.size <= MAX_FILE_SIZE;
}
```

## Documentation

### Code Documentation

#### Python Docstrings

Use Google-style docstrings:

```python
def process_audio(audio_file: str, sample_rate: int) -> np.ndarray:
    """Process audio file for analysis.
    
    Args:
        audio_file: Path to audio file.
        sample_rate: Target sample rate in Hz.
        
    Returns:
        Processed audio as numpy array.
        
    Raises:
        ValueError: If audio file is invalid.
    """
    # Implementation
```

#### TypeScript JSDoc

```typescript
/**
 * Uploads audio file to server
 * @param file - Audio file to upload
 * @returns Upload result with file ID
 */
async function uploadAudio(file: File): Promise<UploadResult> {
  // Implementation
}
```

### Project Documentation

- Update README.md for user-facing changes
- Update docs/ for developer-facing changes
- Update API documentation for backend changes
- Update CHANGELOG.md for significant changes

## Testing

### Test Coverage

- Target: >80% overall coverage
- Critical paths: >90% coverage
- Utilities: >95% coverage

### Test Types

#### Unit Tests

Test individual functions/components in isolation.

#### Integration Tests

Test component interactions with test database.

#### End-to-End Tests

Test complete workflows with test environment.

### Running Tests

#### Backend Tests

```bash
pytest backend/tests/ --cov=backend --cov-report=html
```

#### Frontend Tests

```bash
npm test
```

### Test Naming

```python
def test_audio_processor_load_valid_file():
    """Test loading valid audio file."""
    pass

def test_audio_processor_load_invalid_file_raises_error():
    """Test loading invalid file raises error."""
    pass
```

## Reporting Issues

### Bug Reports

Include the following information:

- Description of the bug
- Steps to reproduce
- Expected behavior
- Actual behavior
- Environment (OS, Python version, etc.)
- Screenshots if applicable

### Feature Requests

Include the following information:

- Description of the feature
- Use case
- Proposed implementation (if known)
- Alternatives considered

## Questions

For questions about the project:

- Check existing documentation
- Search existing issues
- Open a new issue with the "question" label

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

## Contact

For questions or concerns, contact the project maintainers.

---

Thank you for contributing to FAEAP!
