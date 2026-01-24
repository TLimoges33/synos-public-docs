# Contributing to Syn_OS

Thank you for your interest in contributing to Syn_OS! This guide will help you get started.

## 🤝 Ways to Contribute

### 1. Report Bugs
Found a bug? [Open an issue](https://github.com/TLimoges33/Syn_OS/issues/new?template=bug_report.md) with:
- Description of the issue
- Steps to reproduce
- Expected vs actual behavior
- System information (kernel version, RAM, etc.)
- Logs if available

### 2. Suggest Features
Have an idea? [Start a discussion](https://github.com/TLimoges33/Syn_OS/discussions/new?category=ideas) or [open a feature request](https://github.com/TLimoges33/Syn_OS/issues/new?template=feature_request.md).

### 3. Improve Documentation
- Fix typos or unclear explanations
- Add examples or tutorials
- Translate documentation
- Create video tutorials

### 4. Contribute Code
- Fix bugs
- Implement new features
- Optimize performance
- Add tests

### 5. Create GRIMOIRE Labs
Share your expertise by creating training labs for the community!

---

## 🚀 Getting Started

### Prerequisites

```bash
# Required tools
- Git
- Rust (1.75+)
- Python (3.11+)
- Docker
- Build essentials (gcc, make, cmake)

# Install Rust
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# Install Python dependencies
sudo apt install python3-dev python3-pip python3-venv
```

### Fork and Clone

```bash
# Fork the repository on GitHub
# Then clone your fork
git clone git@github.com:YOUR_USERNAME/Syn_OS.git
cd Syn_OS

# Add upstream remote
git remote add upstream git@github.com:TLimoges33/Syn_OS.git
```

### Set Up Development Environment

```bash
# Create Python virtual environment
python3 -m venv venv
source venv/bin/activate

# Install development dependencies
pip install -r development/requirements.txt

# Build Rust components
cargo build --workspace --exclude syn-kernel

# Run tests
cargo test --workspace --exclude syn-kernel
python -m pytest tests/
```

---

## 📝 Development Workflow

### 1. Create a Branch

```bash
# Update your fork
git checkout main
git pull upstream main

# Create feature branch
git checkout -b feature/your-feature-name
# or
git checkout -b fix/bug-description
```

### 2. Make Changes

- Follow the [coding standards](#coding-standards)
- Write tests for new features
- Update documentation
- Keep commits focused and atomic

### 3. Test Your Changes

```bash
# Run all tests
./scripts/03-test/dev/testing/verify-build.sh

# Run specific tests
cargo test -p synos-ai-daemon
python -m pytest tests/test_consciousness.py

# Check formatting
cargo fmt --check
black --check .
```

### 4. Commit Your Changes

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```bash
# Format: <type>(<scope>): <subject>

git commit -m "feat(alfred): add voice command support"
git commit -m "fix(kernel): resolve memory leak in syscall 480"
git commit -m "docs(grimoire): add APT simulation lab guide"
git commit -m "test(security): add eBPF monitor tests"
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation only
- `style`: Code style/formatting
- `refactor`: Code refactoring
- `test`: Adding tests
- `chore`: Maintenance tasks
- `security`: Security improvements

### 5. Push and Create Pull Request

```bash
# Push to your fork
git push origin feature/your-feature-name

# Open a pull request on GitHub
# Fill out the PR template with:
# - Description of changes
# - Related issues
# - Testing performed
# - Screenshots (if UI changes)
```

---

## 🎨 Coding Standards

### Rust

```rust
// Use idiomatic Rust
// Follow clippy suggestions
// Add documentation comments

/// Processes AI stimulus and returns decision
///
/// # Arguments
/// * `stimulus` - The input stimulus data
///
/// # Returns
/// * `Ok(Decision)` on success
/// * `Err(Error)` on failure
pub fn process_stimulus(stimulus: &Stimulus) -> Result<Decision> {
    // Implementation
}

// Run formatters
cargo fmt
cargo clippy -- -D warnings
```

### Python

```python
"""Follow PEP 8 and type hints."""

def process_threat_intel(indicator: str) -> ThreatScore:
    """
    Process a threat intelligence indicator.

    Args:
        indicator: STIX 2.1 indicator object

    Returns:
        ThreatScore with confidence and severity

    Raises:
        ValueError: If indicator format is invalid
    """
    pass

# Run formatters
black .
isort .
mypy src/
```

### Shell Scripts

```bash
#!/usr/bin/env bash
# Use shellcheck for validation
# Add error handling

set -euo pipefail  # Exit on error, undefined vars, pipe failures

# Function documentation
# Description: Builds the ISO image
# Arguments:
#   $1 - Build profile (dev|production)
build_iso() {
    local profile="$1"
    echo "Building ISO with profile: $profile"
    # Implementation
}
```

---

## 🧪 Testing Guidelines

### Test Coverage

- Aim for 80%+ code coverage
- Write unit tests for all new functions
- Add integration tests for components
- Create end-to-end tests for features

### Test Structure

```rust
#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn test_consciousness_state_machine() {
        // Arrange
        let mut consciousness = Consciousness::new();
        
        // Act
        let result = consciousness.process_stimulus(&stimulus);
        
        // Assert
        assert!(result.is_ok());
        assert_eq!(consciousness.state(), State::Awake);
    }
}
```

---

## 📋 Pull Request Guidelines

### Before Submitting

- [ ] Tests pass locally
- [ ] Code follows style guidelines
- [ ] Documentation updated
- [ ] Commit messages follow convention
- [ ] Branch is up-to-date with main

### PR Description Template

```markdown
## Description
Brief description of changes

## Related Issues
Fixes #123
Related to #456

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Testing
- Tested on: Debian 13, 16GB RAM, 8 cores
- Test commands run:
  - `cargo test -p affected-crate`
  - `pytest tests/test_feature.py`

## Screenshots (if applicable)
Attach before/after screenshots

## Checklist
- [ ] Code follows project style
- [ ] Comments added for complex logic
- [ ] Documentation updated
- [ ] Tests added/updated
- [ ] All tests pass
```

---

## 🏆 Recognition

Contributors will be:
- Listed in [CONTRIBUTORS.md](CONTRIBUTORS.md)
- Credited in release notes
- Eligible for contributor badges
- Invited to team discussions

---

## 💬 Communication

- **GitHub Issues**: Bug reports and features
- **GitHub Discussions**: General questions and ideas
- **Email**: synos@tlimoges.dev
- **Discord**: Coming soon!

---

## 📜 Code of Conduct

We are committed to providing a welcoming and inclusive environment. Please read and follow our [Code of Conduct](CODE_OF_CONDUCT.md).

### Our Standards

**Positive behaviors:**
- Being respectful of differing viewpoints
- Gracefully accepting constructive criticism
- Focusing on what is best for the community
- Showing empathy towards other members

**Unacceptable behaviors:**
- Harassment or discriminatory language
- Trolling or insulting comments
- Publishing private information
- Other conduct inappropriate in a professional setting

---

## 📄 License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

## 🙏 Thank You!

Every contribution matters, whether it's:
- A typo fix in documentation
- A critical bug fix
- A new feature
- Helping other users

Your time and effort help make Syn_OS better for everyone!

---

**Questions?** Don't hesitate to ask in [GitHub Discussions](https://github.com/TLimoges33/Syn_OS/discussions)!
