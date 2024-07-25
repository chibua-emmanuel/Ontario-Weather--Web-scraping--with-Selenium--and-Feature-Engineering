# Ontario Weather- Web scraping (with Selenium) and Feature Engineering
 Ontario Weather- Web scraping (with Selenium) and Feature Engineering

# Weather Alerts Scraper

This Python script is designed to scrape weather alert information from the Government of Canada's weather website, specifically targeting alerts for selected provinces. It uses the Selenium and BeautifulSoup libraries to navigate and parse the webpage content, extracting data such as provinces, cities, warnings, and statements, and then saves this data into both CSV and JSON formats.

## Table of Contents

1. [Requirements](#requirements)
2. [Installation](#installation)
3. [Usage](#usage)
4. [Features](#features)
5. [Output](#output)
6. [Troubleshooting](#troubleshooting)
7. [Contributing](#contributing)
8. [License](#license)

## Requirements

Before running the script, ensure you have the following prerequisites installed on your system:

- **Python 3.6+**: This script is compatible with Python version 3.6 and above.
- **Google Chrome**: The script uses the Chrome WebDriver to automate browser tasks.
- **ChromeDriver**: This must match the version of Chrome installed on your system.
- **Python Packages**: The following Python packages are required:
  - `selenium`: For controlling the Chrome browser.
  - `beautifulsoup4`: For parsing HTML content.
  - `pandas`: For data manipulation and exporting.
  - `pytz`: For timezone conversion.

You can install these Python packages using `pip`:

```bash
pip install selenium beautifulsoup4 pandas pytz
```

## Installation

To run the script, follow these steps:

1. **Clone the Repository**:
   
   Clone the repository to your local machine using the following command:

   ```bash
   git clone https://github.com/chibua-emmanuel/Ontario-Weather--Web-scraping--with-Selenium--and-Feature-Engineering.git
   ```

   Navigate to the cloned directory:

   ```bash
   cd weather-alerts-scraper
   ```

2. **Set Up ChromeDriver**:

   - Download the appropriate version of ChromeDriver from the [official site](https://sites.google.com/a/chromium.org/chromedriver/downloads).
   - Extract the `chromedriver` executable and place it in your system's PATH or the same directory as the script.

3. **Run the Script**:

   Execute the Python script using:

   ```bash
   python weather_scraper.py
   ```

## Usage

The script automatically opens a Chrome browser window and navigates to the specified URL to scrape weather alert data. Here's a detailed breakdown of its functionality:

1. **Setup**:

   - Import necessary libraries for web scraping, HTML parsing, data manipulation, and timezone handling.
   - Initialize the Selenium WebDriver for Chrome to automate browser tasks.

2. **Web Scraping**:

   - Open the Government of Canada's weather alerts webpage using Selenium.
   - Parse the page source with BeautifulSoup to extract relevant weather alerts for selected provinces.

3. **Data Extraction**:

   - Extract and store alert details such as provinces, cities, warnings, and statements.
   - Classify alerts as warnings or statements based on predefined lists.
   - Capture the current date and time in Eastern Standard Time (EST).

4. **Data Storage**:

   - Convert the extracted data into a pandas DataFrame.
   - Print the DataFrame to the console for immediate inspection.
   - Save the DataFrame to both CSV and JSON files for further analysis.

### Command Line Arguments (Optional)

While this script does not currently support command-line arguments, you may modify it to accept inputs such as specific provinces or output file names. For more advanced usage, consider wrapping the script in a command-line interface (CLI) tool.

## Features

- **Selective Scraping**: The script targets specific provinces and classifies alerts as warnings or statements.
- **Time Zone Handling**: Automatically adjusts timestamps to Eastern Standard Time (EST) for consistency.
- **Data Export**: Saves scraped data into CSV and JSON formats, allowing easy integration with other tools or processes.
- **Browser Automation**: Utilizes Selenium for efficient and accurate web scraping.

## Output

The script generates two output files in the same directory as the script:

1. **CSV File**: `weather_data.csv`
   
   This file contains structured data in a tabular format with columns for province, city, warning, statement, month, day, date, and time.

2. **JSON File**: `weather_data.json`

   This file stores data in JSON format, suitable for web applications and APIs.

### Sample Output

Here's a sample of what the CSV output might look like:

| Province        | City       | Warning          | Statement | Month     | Day        | Date       | Time     |
|-----------------|------------|------------------|-----------|-----------|------------|------------|----------|
| Ontario         | Toronto    | Extreme cold     | None      | July      | Thursday   | 2024-07-25 | 14:23:45 |
| British Columbia| Vancouver  | None             | Fog       | July      | Thursday   | 2024-07-25 | 14:23:45 |

## Troubleshooting

If you encounter issues while running the script, consider the following troubleshooting tips:

- **ChromeDriver Version Mismatch**: Ensure that your ChromeDriver version matches the installed version of Google Chrome.
- **Webpage Structure Changes**: If the webpage's HTML structure changes, the script may fail to locate elements. Update the `find_all` methods with the correct HTML tags or attributes.
- **Network Issues**: Ensure that your internet connection is stable. If the website is down or inaccessible, the script won't function correctly.
- **Dependencies**: Verify that all required Python packages are installed using `pip list` and reinstall any missing packages.

### Common Errors

- **`selenium.common.exceptions.WebDriverException`**: This error typically occurs if the ChromeDriver executable is not found. Ensure it is correctly placed in your PATH.
- **`AttributeError: 'NoneType' object has no attribute 'text'`**: This error may arise if the expected HTML elements are not found on the page. Check the webpage structure for changes.

## Contributing

Contributions to this project are welcome! Feel free to open issues or submit pull requests on the [GitHub repository](https://github.com/chibua-emmanuel/Ontario-Weather--Web-scraping--with-Selenium--and-Feature-Engineering.git).

### Contribution Guidelines

1. Fork the repository.
2. Create a new branch (`feature/your-feature-name`).
3. Commit your changes (`git commit -m 'Add new feature'`).
4. Push to the branch (`git push origin feature/your-feature-name`).
5. Open a pull request on GitHub.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

This `README` file serves as a comprehensive guide to understanding and using the Weather Alerts Scraper script. For additional support or questions, please contact the repository maintainer.
