# Contributing to Huawei Air Transfer Technology

Thank you for your interest in contributing to HATT! This document explains how to get involved, what we expect, and how the review process works.

---

## Table of Contents

- [Who Can Contribute](#who-can-contribute)
- [Getting Started](#getting-started)
- [Branch Naming](#branch-naming)
- [Making Changes](#making-changes)
- [Commit Messages](#commit-messages)
- [Opening a Pull Request](#opening-a-pull-request)
- [Review Process](#review-process)
- [Code Style](#code-style)
- [Reporting Bugs](#reporting-bugs)
- [Suggesting Features](#suggesting-features)
- [Security Issues](#security-issues)

---

## Who Can Contribute

Anyone is welcome to contribute — whether it is fixing a typo, improving documentation, adding a feature, or reporting a bug. You do not need to be a maintainer to open a pull request.

---

## Getting Started

1. **Fork** this repository to your own GitHub account
2. **Clone** your fork locally:

```bash
git clone https://github.com/YOUR_USERNAME/huawei-air-transfer.git
cd huawei-air-transfer
```

3. **Install dependencies:**

```bash
pip install -r requirements.txt
```

4. **Run the app** to confirm everything works before making changes:

```bash
python src/main.py
```

---

## Branch Naming

Always create a new branch for your changes. Never work directly on `main`.

| Type | Format | Example |
|---|---|---|
| New feature | `feature/your-feature-name` | `feature/gesture-sensitivity-setting` |
| Bug fix | `fix/your-bug-name` | `fix/overlay-not-closing` |
| Documentation | `docs/what-you-changed` | `docs/update-installation-steps` |
| Refactor | `refactor/what-you-changed` | `refactor/network-discovery-module` |

```bash
git checkout -b feature/your-feature-name
```

---

## Making Changes

- Keep your changes focused — one feature or fix per pull request
- Write or update tests where relevant (tests live in `/tests`)
- If you add a new dependency, add it to `requirements.txt`
- Test on your local machine before opening a PR

---

## Commit Messages

Write clear, descriptive commit messages in this format:

```
type: short description of what changed
```

Examples:

```
feat: add gesture sensitivity slider to settings
fix: prevent overlay from freezing on Linux
docs: clarify installation steps for macOS
refactor: simplify device discovery loop
```

Avoid vague messages like `update`, `fix stuff`, or `changes`.

---

## Opening a Pull Request

1. Push your branch to your fork:

```bash
git push origin feature/your-feature-name
```

2. Go to the original repository on GitHub
3. Click **Compare & pull request**
4. Fill in the PR description:
   - What does this change do?
   - Why is it needed?
   - Any known limitations or follow-up work?
5. Target the `main` branch
6. Submit the PR

---

## Review Process

- All changes must come in through a pull request — no direct pushes to `main`
- At least **one maintainer** must approve your PR before it can be merged
- Only the three maintainers (Aminjon, Fadl, islamibragimov) can merge into `main`
- A reviewer may request changes — please respond and update your branch accordingly
- Once approved, a maintainer will handle the merge

---

## Code Style

- Follow **PEP 8** for Python code
- Use clear, descriptive variable and function names
- Add docstrings to new functions and classes
- Keep functions short and focused on a single responsibility
- Comment non-obvious logic

You can check your code with:

```bash
pip install flake8
flake8 src/
```

---

## Reporting Bugs

Open a GitHub Issue and include:

- A clear description of the bug
- Steps to reproduce it
- What you expected to happen vs. what actually happened
- Your OS and Python version
- Any error messages or logs

---

## Suggesting Features

Open a GitHub Issue with the label `enhancement` and describe:

- What the feature does
- Why it would be useful
- Any rough idea of how it could be implemented (optional)

---

## Security Issues

Do **not** open a public issue for security vulnerabilities. Instead, open a private issue or email the maintainers directly. See the [Security section in the README](README.md#security) for more details.

---

*Built at Dushanbe Innovation Institute · 2026*
