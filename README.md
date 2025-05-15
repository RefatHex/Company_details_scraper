# Company Website and Contact Information Scraper

This tool automatically finds company websites and extracts contact information (phone numbers and emails) without manual searching.

## What This Tool Does

- Reads a list of company names from your Excel spreadsheet
- Automatically finds each company's official website
- Extracts contact information (phone numbers and email addresses)
- Saves all gathered information in a easy-to-use CSV file

## Before You Start: Requirements

1. **Install Python**: Download and install Python 3.8 or newer from [python.org](https://python.org)

   - During installation, make sure to check "Add Python to PATH"

2. **Download This Tool**: Make sure you have all the files in this folder

## Step-by-Step Setup Guide

1. **Prepare Your Data**:

   - Create an Excel file (for example, `companies.xlsx`)
   - In the first column, list all company names you want to research
   - Save this Excel file in the same folder as this tool

2. **One-Time Setup** (you only need to do this once):
   - Open Command Prompt (search for "cmd" in Windows start menu)
   - Navigate to this folder by typing:
     ```
     cd path\to\website_details
     ```
   - Install pipenv if you don't have it already:
     ```
     pip install pipenv
     ```
   - Set up the required environment by typing:
     ```
     pipenv install
     ```

## Running the Tool

1. **Open Command Prompt** and navigate to this folder:

   ```
   cd path\to\website_details
   ```

2. **Run the tool with pipenv**:

   ```
   pipenv run python script.py
   ```

   Alternatively, you can activate the pipenv shell first and then run the script:

   ```
   pipenv shell
   python script.py
   ```

3. **Follow the on-screen instructions**:

   - When prompted, enter the name of your Excel file (e.g., `companies.xlsx`)
   - Confirm to begin the process
   - The tool will start collecting information

4. **Get Your Results**:
   - When complete, you'll find a new CSV file in the same folder
   - The filename will be based on your input file (e.g., `companies_contacts.csv`)
   - Open this file with Excel to see all the collected information

## Understanding Your Results

The results CSV file will contain:

- **Company**: The company name from your input file
- **Website**: The URL of the company's official website
- **Contact Numbers**: Any phone numbers found on the website
- **Emails**: Any email addresses found on the website

## Troubleshooting

**If the tool doesn't start:**

- Make sure Python is installed correctly
- Verify all setup steps were completed
- Try restarting your computer

**If you don't see results for some companies:**

- Some companies may not have easily accessible contact information
- Check your internet connection
- The tool creates a log file (`scraper.log`) that can help identify issues

**If the tool stops during processing:**

- Don't worry! The tool saves progress automatically
- Just run it again with the same input file, and it will continue where it left off

## Need Further Help?

If you encounter any issues or have questions about using this tool, please contact the developer who provided it to you.
