# Creating an Executable for Excel AI Analyzer

This guide walks you through the process of creating a standalone executable from your Excel AI Analyzer Python project.

## Prerequisites

- Python installed on your system
- Your Excel AI Analyzer project files
- Internet connection to download required packages

## Step 1: Install PyInstaller

Open a command prompt or terminal and install PyInstaller:

```
pip install pyinstaller
```

## Step 2: Navigate to Your Project Directory

```
cd /Users/amitatias/Desktop/Excel AI Analyzer
```

## Step 3: Identify Your Main Script

Determine which Python file serves as the entry point to your application. This is typically the file you run to start your program (e.g., `main.py`, `app.py`, or `excel_analyzer.py`).

## Step 4: Create the Executable

### Basic Command
For a simple executable that includes all dependencies in a single file:

```
pyinstaller --onefile your_main_script.py
```

Replace `your_main_script.py` with your actual main Python file.

### Enhanced Options
For a more polished application:

```
pyinstaller --onefile --windowed --icon=app_icon.ico your_main_script.py
```

- `--onefile`: Creates a single executable file
- `--windowed`: Prevents a console window from appearing (good for GUI applications)
- `--icon=app_icon.ico`: Sets a custom icon for your executable (optional)

## Step 5: Test Your Executable

After PyInstaller completes, find your executable in the `dist` folder:

```
cd dist
```

Run your executable to test if it works properly.

## Step 6: Package Additional Resources (If Needed)

If your application uses external files (like configuration files, images, etc.), you need to include them:

```
pyinstaller --onefile --add-data "path/to/resource:destination" your_main_script.py
```

For example:
```
pyinstaller --onefile --add-data "config.json:." --add-data "images/:images/" your_main_script.py
```

## Troubleshooting Common Issues

### Missing Modules
If you get "ModuleNotFoundError" when running your executable, specify hidden imports:

```
pyinstaller --onefile --hidden-import=missing_module your_main_script.py
```

### Missing Files at Runtime
Create a spec file first, then edit it to include additional files:

```
pyinstaller --name "Excel AI Analyzer" your_main_script.py
```

Edit the generated `.spec` file and then run:

```
pyinstaller "Excel AI Analyzer.spec"
```

### Large File Size
Use the `--strip` option to reduce the executable size:

```
pyinstaller --onefile --strip your_main_script.py
```

## Complete Example for Excel AI Analyzer

Assuming your main script is named `excel_analyzer.py`:

```
# Install PyInstaller
pip install pyinstaller

# Create a basic executable
pyinstaller --onefile excel_analyzer.py

# OR create a more polished executable (for GUI)
pyinstaller --onefile --windowed --icon=app_icon.ico excel_analyzer.py

# Find your executable in the 'dist' folder
```