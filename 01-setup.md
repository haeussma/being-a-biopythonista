# Being a digital biochemist in 2026 - an opinionated guide to get started

## 0. Basic setup 

Before we touch Python, sequence, or meaurement data, we need a sane coding environment.  
Most beginner pain in Python does *not* come from coding itself — it comes from bad tooling.

This section sets up a minimal, state of the art, and future-proof stack that works the same across platforms.

---

## Why you need a proper code editor

A code editor provides a lot of features that make coding easier and more efficient. It highlights syntax errors, provides autocompletion, and integrates with version control systems.

### Recommended editor: Cursor
Cursor is a VS-Code–based editor with first-class AI support.

- Website: https://cursor.com/download
- Platforms: macOS, Linux, Windows
- Why Cursor:
  - excellent Python support
  - integrated file browser
  - built-in AI that understands your codebase, explains code, and helps you write code

> [!NOTE]
> If you already use VS Code confidently or another editor, you can keep it. For everyone else: Cursor is the shortest path to productivity in 2026.
---

## Platform-specific setup

### Windows: use Windows Subsystem for Linux (WSL) (mandatory)

**Do not develop Python code directly on Windows.**

Many Python tools assume assume Unix-like environment and file paths, which is not the case on Windows.

WSL gives you a real Linux environment running natively on Windows.


#### Install WSL
Install WSL from the Microsoft Store or follow the official guide: https://learn.microsoft.com/windows/wsl/install

---

### macOS: Homebrew + native Unix

macOS is already Unix-based, but you still need a package manager.

#### Install Homebrew
Homebrew installs system tools cleanly and reproducibly. Find installation instructions here: https://brew.sh

---

### Linux: native is fine

If you’re on Linux, you're good to go.

---

## Python package management (important)

### Use `uv` (recommended)


`uv` is a fast, modern Python tool that handles code dependencies and environments.

### Install `uv`
- https://docs.astral.sh/uv/

## 1. Create a Python project

Coding project are self-contained and everything related to a project is stored in a single directory. It is a common practice to create a code project folder in your home directory, which contains all your projects.  

For this first example, we create a new project from. Inside cursor you can eigther open an existing project (folder) or create a new one. In this we create a new project. Therefore, select `File` > `New Folder` and call it e.g. "python-101".

Inside Cursor, you are presented with a file browser on the left side of the screen. This is where you can create and manage files and folders. On the right side, you have an AI-powered chat interface, which enables you to generate or learn about code.

To get started, hover over the file browser on the left hand side and click on the new file icon. A text field appears where the name of the file can be entered. Call it call it e.g. "basics.ipynb".

> [!NOTE]
> The `.ipynb` file extension is a Jupyter Notebook file. It is a special file format that allows to create code cells you to create and share documents that contain live code, equations, visualizations and narrative text. It is like a combination of a text editor and a Python interpreter.

## 2. Wire up a Python environment to the project

Every coding project requires a dedicated Python environment - a defined set of packages installed specifically for that project. Because different projects depend on different package versions, using separate environments prevents conflicts and keeps projects reproducible. This is where `uv` comes in.

To create and activate a new Python environment, open a new terminal by naviating to `Terminal` > `New Terminal`.

Enter the following command to create a new Python environment:

```bash
uv venv
```

This will create a new virtual environment (venv) in the project directory. You can see the environment in the file browser on the left hand side called `.venv`.

To activate the environment for the current terminal session, enter the following command:

```bash
source .venv/bin/activate
```

To make the environment work with our Jupyter Notebook, we need to install the `ipykernel` package. Enter the following command to add the package to the environment:

```bash
uv pip install ipykernel
```

Now, we need to tell the Jupyter Notebook to use this environment. Enter the following command to register the environment. Therefore, open the previously create Jupyter Notebook `basics.ipynb` by clicking on in the file browser. Then click on the `Select Kernel` button in the top right corner of the notebook. Select `Python Environments...` > `★.venv (Python ...)`.
Now, all initial setup is done and we can start coding.

## 3. Write your first Python code

Nextup, we will touch Python fundamentals including:
- variables
- data types
- lists
- dictionaries
- loops 
- ...

[@jr-1991](https://github.com/jr-1991) has prepared a comprehensive minimalistic Python tutorial, covering the most important concepts.

The most important concepts are:
- [Fundamentals](https://jr-1991.github.io/PythonProgramming2025/notes/Seminar_001/)
- [Functions in Python](https://jr-1991.github.io/PythonProgramming2025/notes/Seminar_003/)

Open one of the websites and read through the content. Type the code yourself and understand what you are doing. Within the notebook that we have created, you can add new code cells by clicking on the `+` button in the top left corner of the notebook. To run a code cell, you can either click on the `Run` button in the top right corner of the cell or press `Shift + Enter`. The output (result) of the code cell will be displayed below the cell.

> [!NOTE]
> Don't just copy, paste, and run the code. Type it yourself and understand what you are doing. This will help you to remember the code and to understand the concepts better.

> [!NOTE]
> You can also use the AI assistant on the right side of the screen to ask questions about the code you are writing. Generally writing code is nowadays heavily supported by AI, which can help finding solution and doing simple repetitive code implmentations. However, basic understanding of the code and the concepts is still required to make sure the generated code is correct and does what you want it to do. As a beginner, it is all about finding the right balance between using the AI and understanding the code and the concepts!

## 4. Working with Python packages

Python packages are a way to organize and share / reuse code for a specific purpose. They are installed using the `uv` tool in order to be used in the currently active project. In general, packages only need to be installed once per project. One of the most commonly used packages are:
- `numpy` for numerical computing
- `matplotlib` for plotting
- `pandas` for spreadsheet-like data manipulation
- `scipy` for scientific computing

To install these packages, first open a new terminal by naviating to `Terminal` > `New Terminal`. Then enter the following command to install the packages:

```bash
uv pip install numpy matplotlib pandas scipy
```

After adding new packages to the environment, Jupyter Notebook needs to be restarted to make the packages available. Therefore, click on the `Kernel` > `Restart Kernel` button in the top right corner of the notebook.

### Use `numpy` a `matplotlib` to plot data

Now, we can use the packages to plot data. For example, to plot the sine function, you can use the following code:

```python
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(0, 10, 100)
y = np.sin(x)
plt.plot(x, y)
plt.show()
```

and also save the plot to a file:

```python
plt.savefig('sine.png')
```

Now, you can open the `sine.png` file in the file browser on the left hand side.

> [!NOTE]
> Try to add the cosine function to the existing plot and add labels to the axes. Think of other ways to manipulate the plot or add additional labels or annotations. To realize these changes you can eighter use the integrated AI-chat, any other chat bot or google how to do it.

