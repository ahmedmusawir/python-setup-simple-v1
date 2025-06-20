# 🛠️ Simple Python Project Setup on Ubuntu VM

This guide will help you set up a Python project **the Stark way** — with isolated environments, version control, and easy dependency management.
Great for deploying, testing, or just tinkering on your Ubuntu VM.

---

## 1. **Clone Your Project Repo**

```bash
git clone https://github.com/ahmedmusawir/my-project.git
cd my-project
```

*Clones your codebase and moves you into the project folder.*

---

## 2. **Check pyenv Installation**

```bash
pyenv --version
# Expected: pyenv 2.5.4
```

*Verifies that `pyenv` is installed, so you can manage multiple Python versions easily.*

---

## 3. **Set Local Python Version**

```bash
pyenv local 3.12.3
python --version
# Expected: Python 3.12.3
```

*Locks this project to Python 3.12.3 using `pyenv`. Every command in this folder now uses that Python version.*

---

## 4. **Create and Activate Virtual Environment**

```bash
python -m venv .venv
source .venv/bin/activate
```

* **`.venv`** keeps your dependencies isolated from the rest of the system.
* **`source .venv/bin/activate`** activates the venv (your shell prompt will change).

---

## 5. **Generate requirements.txt (If Needed)**

If you’re setting up a new project and want to save your current packages:

```bash
pip freeze > requirements.txt
```

* **Pro tip:**
  Only do this if you’re in the original repo with all the needed dependencies installed.
  If you already have a `requirements.txt`, you can skip this.

---

## 6. **Install All Dependencies**

```bash
pip install -r requirements.txt
```

* Installs all the packages your project needs into the active virtual environment.

---

## 7. **Upgrade pip (Recommended)**

```bash
pip install --upgrade pip
```

* Keeps your package installer up-to-date and less buggy.

---

## 8. **You’re Ready to Code!**

* Run your Python scripts as usual — you’re in an isolated, fully-configured dev environment.

---

## 📝 **Bonus Tips**

* **Deactivate venv:**
  When done, type `deactivate` to exit the virtual environment.
* **Check venv status:**
  If your shell shows `(.venv)`, it’s active.
* **Delete venv:**
  Just delete the `.venv` folder: `rm -rf .venv` (no impact on your code or requirements.txt).
* **Switch Python versions:**
  Use `pyenv local <version>` anytime.

---

## 🧑‍💻 **Troubleshooting**

* If `pyenv` is not found, install it via their [official guide](https://github.com/pyenv/pyenv#installation).
* For missing Python builds:

  ```bash
  pyenv install 3.12.3
  ```
