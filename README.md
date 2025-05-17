# Company Contact Scraper

An efficient multi-threaded web scraper for extracting company contact information.

## Features

- Batch processing of company data (10 companies per batch)
- Multi-threaded execution for improved performance
- Intelligent contact information extraction
- Detailed logging system
- Result export to Excel

## Prerequisites

- Python 3.8 or higher
- Google Chrome browser
- Windows operating system

## Installation

1. Clone this repository
2. Install required dependencies:

```bash
pip install -r requirements.txt
```

## Required Input

Place your input file `sheet.xlsx` in the project root directory. The file should contain a list of company names to process.

## Usage

### Option 1: Using Batch File

Simply run:

```bash
run_scraper.bat
```

### Option 2: Manual Execution

```bash
python main.py
```

## Output Files

- `results.xlsx`: Contains scraped company data
- `scraping.log`: General execution logging
- `scraper.log`: Detailed processing logs

## Dependencies

```
pandas==2.1.0
selenium==4.15.2
beautifulsoup4==4.12.2
requests==2.31.0
fake-useragent==1.4.0
tldextract==5.1.1
openpyxl==3.1.2
urllib3==2.0.7
```

## Process Flow

1. Reads company names from input Excel file
2. Processes companies in batches of 10
3. For each company:
   - Searches for official website
   - Analyzes website content
   - Extracts contact information
4. Saves results to Excel file

## Logs

- Check `scraping.log` for high-level execution information
- Check `scraper.log` for detailed processing logs

## Error Handling

- Automatic retry mechanism for failed requests
- Timeout handling for unresponsive websites
- Detailed error logging

## Contributing

Feel free to submit issues and enhancement requests.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
