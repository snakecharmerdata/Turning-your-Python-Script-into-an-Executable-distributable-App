
# Quick Reference: Converting Python to Executable
## Essential Commands.

This quick reference guide shows the bare minimum commands needed to convert a Python script into an executable on both macOS and Windows.

## For macOS

```bash
# STEP 1: Install PyInstaller
pip install pyinstaller

# STEP 2: Navigate to your project folder
cd ~/Desktop/Excel\ AI\ Analyzer

# STEP 3: Create the executable
pyinstaller --windowed --onefile excel_ai_analyzer.py

# STEP 4: Package for distribution (optional)
cd dist
(then type in to the terminal the below.)
zip -r "Excel AI Analyzer.zip" "Excel AI Analyzer.app"
```

> **What to type in Terminal:** Just copy and paste each command, replacing the folder and file names with your own.

## For Windows

```
# STEP 1: Install PyInstaller
pip install pyinstaller

# STEP 2: Navigate to your project folder
cd C:\Users\YourName\Desktop\Excel AI Analyzer

# STEP 3: Create the executable
pyinstaller --windowed --onefile excel_ai_analyzer.py
```

> **What to type in Command Prompt:** Just copy and paste each command, replacing the folder and file names with your own.

## Including Additional Files (Both Platforms)

```bash
# For macOS:
pyinstaller --windowed --onefile --add-data "config.json:." excel_ai_analyzer.py

# For Windows:
pyinstaller --windowed --onefile --add-data "config.json;." excel_ai_analyzer.py
```

> **Note:** The only difference is the separator: macOS uses colon (:) while Windows uses semicolon (;).

## Most Common Options

- `--windowed`: No console window appears when the application runs
- `--onefile`: Package everything into a single file
- `--name`: Specify a custom name for the output
- `--add-data`: Include additional files
- `--hidden-import`: Manually include a Python module

## Finding Your Executable

Your executable will be in the `dist` folder that PyInstaller creates in your project directory:

- macOS: `dist/YourAppName.app`
- Windows: `dist/YourAppName.exe`
