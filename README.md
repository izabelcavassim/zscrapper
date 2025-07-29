
# Zillow Scrapper

## Installing Dependencies

### Pre-requisites

- **Python 3.10 or newer** installed on your system.
- **Poetry** installed for dependency management.
- Optionally, **pyenv** to manage multiple Python versions (recommended).

---

### Step 1: Check Python Version

Make sure you have Python 3.10 or higher:

```bash
python --version
```

If your version is lower than 3.10, proceed to Step 2 to install and configure `pyenv`.

---

### Step 2 (Optional but Recommended): Install and Use `pyenv` to Manage Python Versions

#### 2.1 Install `pyenv`

If you don’t have `pyenv` installed, install it via Homebrew (macOS):

```bash
brew install pyenv
```

#### 2.2 Configure your shell for `pyenv`

Add these lines to your shell config file (e.g., `.bashrc`, `.zshrc`):

```bash
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init --path)"
eval "$(pyenv init -)"
```

Then restart your terminal or run:

```bash
source ~/.zshrc  # or source ~/.bashrc depending on your shell
```

#### 2.3 Install Python 3.10.14 (example)

```bash
pyenv install 3.10.14
```

#### 2.4 Set Python 3.10.14 locally for this project

Inside your project directory:

```bash
pyenv local 3.10.14
```

This makes sure Python 3.10.14 is used whenever you are in the project folder.

---

### Step 3: Install Poetry

If you don't have Poetry installed, run:

```bash
curl -sSL https://install.python-poetry.org | python3 -
```

Make sure Poetry is in your PATH (you might need to restart your terminal or add it manually).

Check Poetry is installed:

```bash
poetry --version
```

---

### Step 4: Configure Poetry to Use Correct Python Version

Ensure Poetry uses the Python 3.10 interpreter:

```bash
poetry env use python
```

*(This uses the Python version active in your shell, which should be 3.10+)*

---

### Step 5: Install Project Dependencies

Inside the project directory, run:

```bash
poetry install
```

This will:

- Create a new virtual environment (if not already created)
- Install all dependencies listed in `pyproject.toml`

---

### Step 6: Activate the Virtual Environment (Optional)

You can activate the Poetry-managed virtual environment with:

```bash
poetry shell
```

Or run commands inside the environment without activating:

```bash
poetry run python scrapper.py
```

## Testing

To run tests, run them inside the Poetry environment:

```bash
poetry run pytest
```