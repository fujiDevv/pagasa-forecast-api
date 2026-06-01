# Contributing to PAGASA Forecast API

First off, thank you for considering contributing to the PAGASA Forecast API! It's people like you that make open-source tools great.

## How Can I Contribute?

### Reporting Bugs
If you find a bug, please create an issue on GitHub with:
- A clear and descriptive title.
- Steps to reproduce the issue.
- Expected vs. actual behavior.
- Python version and OS used.

### Suggesting Enhancements
Have an idea for a new feature? We'd love to hear it! Open an issue and describe your suggestion in detail, including why you think it would be useful.

### Pull Requests
We welcome pull requests for bug fixes, features, and documentation improvements.
1. Fork the repository and create your branch from `main`.
2. Ensure you have activated your virtual environment and installed dependencies from `requirements.txt`.
3. If you've added or modified code, verify that it runs locally using `python local_server.py`.
4. Ensure your code follows the existing style conventions.
5. Create a pull request describing the changes you've made.

## Setting Up Locally

1. Fork and clone the repository.
2. Create a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate # For Windows, use `venv\Scripts\activate`
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Start the local dev server:
   ```bash
   python local_server.py
   ```

## Code Style
Please keep your code clean and readable. We currently don't enforce a strict linter, but standard PEP-8 guidelines are heavily encouraged.
