## Project Setup with Poetry and Jupyter Notebook

This guide explains how to set up a Python project using Poetry for dependency management and Jupyter Notebook for interactive development.

### **1. Install Poetry**
First, install Poetry if you haven't already:

- **On Linux/macOS**:
  ```bash
  curl -sSL https://install.python-poetry.org | python3 - --version 2.1.1
  ```

- **On Windows** (via PowerShell): (TODO: add version as above)
  ```powershell
  (Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicP) | python -
  ```

---

### **2. Install dependencies**

1. Clone and cd to this repo
   ```bash
   cd this_project
   ```

2. Install deps with Poetry:
   ```bash
   poetry install
   ```

---

### **3. Setup Jupyter Kernel**

1. Activate the Poetry environment:
   ```bash
   poetry shell
   ```

2. Source the file
   ```bash
   # source ../bin/activate
   ```

---

### **4. Launch Jupyter Notebook**

Start Jupyter Notebook:
```bash
jupyter notebook
```

- In the Jupyter interface, go to **Kernel > Change Kernel** and select **"Python (my_project)"** to use the Poetry environment.

---

### **5. Verify the Setup**

1. In a Jupyter notebook, check that the correct Python environment is being used:
   ```python
   import sys
   print(sys.executable)
   ```

   This should point to the Python executable within the Poetry virtual environment.

---

### **6. Day-to-Day Workflow**

- To activate the Poetry environment:
  ```bash
  poetry shell # (and source...)
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
