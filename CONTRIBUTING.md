# Contributing to Compiler Design Implementation Suite

Thank you for investing your time in improving **Compiler Design Implementation Suite**!

This document provides a set of guidelines and best practices for contributing to this open-source project.

---

## Code of Conduct

By participating in this project, you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md). Please report unacceptable behavior following the guidelines in that document.

---

## How Can I Contribute?

### Reporting Bugs
Before creating bug reports, please check the existing [Issues](https://github.com/Akhil-Binu/Compiler-Lab/issues) list. If you find a new bug, please open an issue using the [Bug Report template](.github/ISSUE_TEMPLATE/bug_report.md) including:
- Clear and descriptive title
- Steps to reproduce
- Expected vs. actual behavior
- Device, OS, and browser/runtime environment specs
- Any relevant logs or screenshots

### Suggesting Enhancements
Feature requests are tracked in GitHub Issues. Please use the [Feature Request template](.github/ISSUE_TEMPLATE/feature_request.md) and describe:
- The problem your enhancement addresses
- The proposed solution and alternative solutions considered
- Context on how it benefits end users

### Code Contributions
1. Fork the repo and clone it locally.
2. Create a new topic branch from `main`:
   ```bash
   git checkout -b feat/your-feature-name
   ```
3. Test your changes locally to ensure there are no breaking changes or errors.
4. Commit using the [Conventional Commits](https://www.conventionalcommits.org/) convention:
   - `feat: add new feature capability`
   - `fix: resolve edge-case validation bug`
   - `docs: update setup instructions in README`
   - `refactor: optimize performance in core module`
5. Push to your fork:
   ```bash
   git push origin feat/your-feature-name
   ```
6. Submit a Pull Request targeting `main`.

---

## Coding Standards

- **C Standards**: Follow standard C99/POSIX socket conventions with clean memory management (freeing allocated buffers) and zero compiler warnings with `-Wall -Wextra`.
- **Commit Discipline**: Keep commits focused and atomic.
- **Documentation**: If adding features or changing behaviors, update the `README.md` accordingly.

---

## Pull Request Checklist

Before submitting your PR, ensure:
- [ ] Code follows existing formatting and style conventions.
- [ ] Changes have been tested locally.
- [ ] No extraneous build files, logs, or secrets are committed.
- [ ] The PR description outlines what was changed, why, and includes screenshots for UI changes.
