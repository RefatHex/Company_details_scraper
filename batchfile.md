# Website Scraper Batch File Explanation

This document explains the functionality of the `run_scraper.bat` file line by line.

## Batch File Overview

The batch file automates the process of setting up the Python environment and running the website scraper script.

## Line-by-Line Explanation

```bat
@echo off
```
- Turns off the display of commands in the console, providing cleaner output.

```bat
echo ========================================
echo Company Website and Contact Info Scraper
echo ========================================
echo.
```
- Displays a title header for the application.
- The `echo.` command creates a blank line for better readability.

```bat
:: Check if Python is installed
python --version > nul 2>&1
```
- Comment indicating that the following code checks for Python installation.
- Runs the Python version command and redirects both standard output (`> nul`) and error output (`2>&1`) to null.

```bat
if %errorlevel% neq 0 (
  echo Python is not installed or not in PATH.
  echo Please install Python from https://www.python.org/downloads/
  echo During installation, make sure to check "Add Python to PATH"
  echo.
  pause
  exit /b 1
)
```
- Checks if the previous command failed (Python not found).
- If Python isn't installed, displays installation instructions.
- Pauses the script to allow reading the message.
- Exits the script with error code 1.

```bat
echo Step 1: Checking for pipenv...
pip show pipenv > nul 2>&1
```
- Displays progress message for Step 1.
- Checks if the pipenv package is installed.

```bat
if %errorlevel% neq 0 (
  echo Installing pipenv...
  pip install pipenv
```
- If pipenv isn't installed (error code not 0), attempts to install it.

```bat
  if %errorlevel% neq 0 (
    echo Failed to install pipenv. Please try manually:
    echo pip install pipenv
    pause
    exit /b 1
  )
```
- Checks if pipenv installation failed.
- If installation fails, shows instructions for manual installation.
- Pauses to allow reading the error message.
- Exits with error code 1.

```bat
) else (
  echo pipenv is already installed.
)
```
- If pipenv is already installed, displays a confirmation message.

```bat
echo.
echo Step 2: Setting up the environment...
pipenv install
```
- Displays a blank line and progress message for Step 2.
- Runs pipenv install to create the virtual environment and install dependencies from the Pipfile.

```bat
if %errorlevel% neq 0 (
  echo Failed to set up the environment. Please check for errors above.
  pause
  exit /b 1
)
```
- Checks if environment setup failed.
- If it failed, shows an error message and exits with error code 1.

```bat
echo.
echo Step 3: Running the scraper...
echo.
pipenv run python script.py
```
- Displays progress message for Step 3.
- Runs the Python script within the pipenv virtual environment.

```bat
if %errorlevel% neq 0 (
  echo The script encountered an error. Please check the logs for details.
)
```
- Checks if the script execution failed.
- If it failed, displays an error message.

```bat
echo.
echo Process completed.
echo Results are saved in the current folder.
echo.
pause
```
- Displays completion messages.
- Informs where results are saved.
- Pauses the script to keep the window open until the user presses a key.

## Usage

To use the scraper:
1. Double-click the `run_scraper.bat` file
2. Follow any on-screen prompts
3. Wait for the scraper to complete its process
4. Check the current folder for the results
