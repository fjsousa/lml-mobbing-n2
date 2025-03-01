## Project Setup with Poetry and Jupyter Notebook

This guide explains how to set up a Python project using Poetry for dependency management and Jupyter Notebook for interactive development.

### **1. Install Poetry**
First, install Poetry if you haven't already:

- **On Linux/macOS**:
  ```bash
  curl -sSL https://install.python-poetry.org | python3 -
  ```

- **On Windows** (via PowerShell):
  ```powershell
  (Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicP) | python -
  ```

Follow the prompts and restart your terminal to ensure Poetry is available.

---

### **2. Create and Initialize Your Project**

1. Create a new project directory:
   ```bash
   mkdir my_project
   cd my_project
   ```

2. Initialize the project with Poetry:
   ```bash
   poetry init
   ```
   Follow the prompts to set up project metadata (name, version, description, etc.).

---

### **3. Add Dependencies**

1. Add core dependencies for your project:
   ```bash
   poetry add numpy pandas matplotlib
   ```

2. Add Jupyter Notebook as a dependency:
   ```bash
   poetry add notebook
   ```

3. Optionally, add development tools like linters and testing libraries:
   ```bash
   poetry add --dev black flake8 pytest
   ```

---

### **4. Set Up Jupyter Kernel**

To ensure Jupyter uses the Python environment from Poetry, follow these steps:

1. Add `ipykernel` to the project:
   ```bash
   poetry add ipykernel
   ```

2. Activate the Poetry environment:
   ```bash
   poetry shell
   ```

3. If this doesn't activate the environment try:
   ```bash
   poetry env info --path
   # source ../bin/activate
   ```

---

### **5. Launch Jupyter Notebook**

Start Jupyter Notebook:
```bash
jupyter notebook
```

- In the Jupyter interface, go to **Kernel > Change Kernel** and select **"Python (my_project)"** to use the Poetry environment.

---

### **6. Verify the Setup**

1. In a Jupyter notebook, check that the correct Python environment is being used:
   ```python
   import sys
   print(sys.executable)
   ```

   This should point to the Python executable within the Poetry virtual environment.

---

### **7. Example Project Structure**

Your project should have a structure like this:

```
my_project/
├── my_project/           # Main package folder
│   ├── __init__.py
│   └── main.py           # Entry point for your project (optional)
├── notebooks/            # Jupyter notebooks
│   └── analysis.ipynb    # Example notebook
├── tests/                # Test folder
│   └── test_main.py      # Example test
├── pyproject.toml        # Managed by Poetry
├── README.md             # Project description
├── .gitignore            # Ignore unnecessary files
└── .env                  # Environment variables (optional)
```

---

### **8. Gitignore**

Create a `.gitignore` file to exclude unnecessary files:
```
# .gitignore
__pycache__/
*.pyc
*.pyo
*.ipynb_checkpoints/
venv/
.env
```

---

### **9. Day-to-Day Workflow**

- To activate the Poetry environment:
  ```bash
  poetry shell
  ```
- To add new dependencies:
  ```bash
  poetry add <package>
  ```
- To run tests (if using `pytest`):
  ```bash
  pytest tests/
  ```
- To format and lint code:
  ```bash
  black my_project/
  flake8 my_project/
  ```

---

### **Troubleshooting**

- If the Jupyter kernel isn't showing, make sure the Poetry environment is activated and re-run the `ipykernel install` command.
- If `poetry shell` does not activate automatically, manually activate the virtual environment:
  ```bash
  source /home/fsousa/.cache/pypoetry/virtualenvs/your-env-name/bin/activate

  source /home/fsousa/.cache/pypoetry/virtualenvs/1-micrograd-wbWMg9m4-py3.10/bin/activate

  ```






