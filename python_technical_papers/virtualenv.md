# Technical Report: Python Virtual Environment

## 1. Introduction

A virtual environment is an isolated Python environment used to manage the dependencies of a project separately from the system Python installation and other projects.

---

## 2. Why Use a Virtual Environment?

Virtual environments help to:

- Isolate project dependencies.
- Avoid package version conflicts.
- Keep the global Python environment clean.
- Use different package versions for different projects.
- Make projects easier to reproduce and maintain.

---

## 3. Creating a Virtual Environment

Python provides the built-in venv module.

```
python3 -m venv venv

Here:

- `python3` → Python interpreter.
- `-m venv` → Runs the virtual environment module.
- `venv` → Name of the environment.
```
## 4. Activating the Environment

### Linux / macOS

```
source venv/bin/activate
````

### Windows

```
venv\Scripts\activate
```

After activation, (venv) appears in the terminal.

## 5. Installing Packages

Packages can be installed using pip.

```
pip install requests
```

Check installed packages:

```bash
pip list
```

## 6. Managing Dependencies

Save project dependencies in requirements.txt:

```
pip freeze > requirements.txt
```

Install all dependencies later:

```
pip install -r requirements.txt
```

This helps recreate the same project environment on another machine.

## 7. Checking the Environment

Check the Python version:

```
python --version
```

On Linux/macOS, check which Python executable is being used:

```
which python
```

The path should point to the virtual environment.

## 8. Deactivating the Environment

When the work is finished:

```
deactivate
```

This returns the terminal to the system Python environment.

## 9. Virtual Environment and Git

The virtual environment should generally not be committed to Git because it contains installed packages and environment-specific files.

Add it to .gitignore:

```
venv/
```

Commit requirements.txt instead.

## 10. Typical Project Structure

```
my_project/
├── venv/
├── requirements.txt
├── .gitignore
└── main.py
```

## 11. Important Commands List

### Create virtual environment
```
python3 -m venv venv
```

### Activate — Linux/macOS
```
source venv/bin/activate
```


### Activate — Windows
```
venv\Scripts\activate
```


### Check Python version
```
python --version
```


### Check Python executable — Linux/macOS
```
which python
```


### Install a package
```
pip install package_name
```


### Install multiple packages
```
pip install pandas numpy matplotlib
```


### List installed packages
```
pip list
```


### Show package details
```
pip show package_name
```


### Save dependencies
```
pip freeze > requirements.txt
```


### Install dependencies
```
pip install -r requirements.txt
```


### Upgrade a package
```
pip install --upgrade package_name
```


### Uninstall a package
```
pip uninstall package_name
```


### Deactivate virtual environment
```
deactivate
```


### Delete virtual environment — Linux/macOS
```
rm -rf venv
```
