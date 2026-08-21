# Technical Report: pip Package Manager in Python

## 1. Introduction

pip is the standard package management tool for Python. It is used to install, update, remove, and manage Python packages.

### Example

```
pip install requests
```

---

## 2. pip Version

### 2.1 Check pip Version

Used to check whether pip is installed and to display its version.

```
pip --version
```

### Example Output

```
pip 25.x.x
```

---

## 3. Installing Packages

### 3.1 Install a Package

Used to install a Python package.

```
pip install requests
```

### 3.2 Install Multiple Packages

Multiple packages can be installed using a single command.

```
pip install numpy pandas matplotlib
```

### 3.3 Install a Specific Version

Used when a project requires a particular version of a package.

```
pip install requests==2.32.0
```

### 3.4 Install a Package from a Requirements File

Packages listed in requirements.txt can be installed using:

```
pip install -r requirements.txt
```

---

## 4. Managing Packages

### 4.1 List Installed Packages

pip list displays all packages installed in the current Python environment.

```
pip list
```

### Example Output

```
Package      Version
------------ -------
numpy        2.x.x
requests     2.32.0
```

### 4.2 Show Package Information

pip show displays detailed information about a specific package.

```
pip show requests
```

It can display:

* Package name
* Version
* Summary
* Installation location
* Dependencies

### 4.3 Uninstall a Package

Used to remove an installed package.

```
pip uninstall requests
```

### 4.4 Upgrade a Package

Used to upgrade a package to a newer available version.

```
pip install --upgrade requests
```

---

## 5. Package Versions

### 5.1 Install a Specific Version

A specific package version can be installed using ==.

```
pip install requests==2.32.0
```

### 5.2 Check Installed Version

The installed version can be checked using:

```
pip show requests
```

or:

```
pip list
```

### 5.3 Check Outdated Packages

Used to find packages that have newer versions available.

```
pip list --outdated
```

---

## 6. pip freeze

pip freeze displays installed packages along with their exact versions.

```
pip freeze
```

### Example

```
numpy==2.x.x
requests==2.32.0
```

This is useful for recording the dependencies of a project.

---

## 7. requirements.txt

requirements.txt is a file used to store the Python packages and versions required by a project.

### 7.1 Create requirements.txt

The installed packages can be saved using:

```
pip freeze > requirements.txt
```

### Example requirements.txt

```
numpy==2.x.x
requests==2.32.0
matplotlib==3.x.x
```

### 7.2 Install Requirements

All packages listed in the file can be installed using:

```
pip install -r requirements.txt
```

This is useful when setting up the project on another computer.

---

## 8. pip with Virtual Environment

pip is commonly used inside a virtual environment so that project dependencies remain isolated.

### Example

```
python3 -m venv venv
source venv/bin/activate

pip install requests
```

### Workflow

```
Create Virtual Environment
          ↓
       Activate
          ↓
    Install Packages
          ↓
    Develop Project
          ↓
 Create requirements.txt
```

---

## 9. Upgrade pip

pip itself can be upgraded using:

```
python -m pip install --upgrade pip
```

Using `python -m pip` helps ensure that pip is executed using the selected Python interpreter.

---

## 10. Installing Packages without a Virtual Environment

Packages can technically be installed directly into the global Python environment.

```
pip install requests
```

However, for project development, using a **virtual environment** is recommended because it prevents dependency conflicts between projects.

---

## 11. Package Dependencies

A package may depend on other Python packages.

For example:

```
Project
   ↓
requests
   ↓
Dependencies
```

When pip installs a package, it can also install its required dependencies.

### Example

```
pip install requests
```

pip resolves and installs the required dependencies when necessary.



