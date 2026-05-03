# IT23860100_ITPM_Assignment
Playwright automation for ITPM assignment

# Test Automation UI - Image Preview Test

## Project Overview

This project contains automated UI tests for validating image preview functionality in the Pixels Suite web application. The test uses **Playwright** with Python to automate browser interactions and verify that image previews are correctly displayed when uploading PNG files.

## Prerequisites

Before running the tests, ensure you have the following installed on your system:

- **Python 3.7+** - [Download Python](https://www.python.org/downloads/)
- **pip** (Python package manager) - Usually included with Python
- **Git** (optional, for cloning the repository)

## Installation

### 1. Clone or Download the Repository

```bash
# If using Git
git clone [GIT_REPOSITORY_LINK]
cd test_automation_ui

# Or navigate to the test_automation_ui folder
cd test_automation_ui
```

### 2. Install Python Dependencies

Install the required Python packages using pip:

```bash
pip install -r requirements.txt
```

**Note:** If `requirements.txt` is not present, install Playwright manually:

```bash
pip install playwright
playwright install chromium
```

The `playwright install chromium` command downloads the necessary browser binaries for automated testing.

## Running the Tests

### Basic Usage

Run the test with default settings:

```bash
python image_preview_test.py
```

### Advanced Options

The test script supports the following command-line arguments:

| Argument | Default | Description |
|----------|---------|-------------|
| `--url` | `https://www.pixelssuite.com/convert-to-png` | Target URL to test |
| `--png` | `webApp.png` | Path to the PNG file to upload |
| `--out-dir` | `results` | Directory to save test results and screenshots |
| `--csv` | `execution_results.csv` | CSV file to store test results |
| `--headless` | `False` | Run browser in headless mode (no GUI) |
| `--timeout-ms` | `60000` | Test timeout in milliseconds |
| `--slow-mo-ms` | `0` | Slow down browser actions (ms per action) |

### Example Commands

```bash
# Run test with headless mode enabled
python image_preview_test.py --headless

# Run test with a custom URL and timeout
python image_preview_test.py --url https://example.com --timeout-ms 120000

# Run test with slower browser actions (useful for debugging)
python image_preview_test.py --slow-mo-ms 1000

# Run test and save results to a custom directory
python image_preview_test.py --out-dir ./my_results --csv ./my_results/test_results.csv
```

## Test Workflow

1. **Initialization** - Launches a Chromium browser and navigates to the target URL
2. **File Upload** - Locates the file input element and uploads the specified PNG file
3. **Preview Detection** - Checks if a preview is rendered and visible in the DOM
4. **Validation** - Determines if the test passed (preview detected) or failed
5. **Reporting** - Captures a screenshot and logs results to CSV

## Output Files

After running the test, the following files are generated:

- **results/preview_pass.png** - Screenshot if test passes
- **results/preview_fail.png** - Screenshot if test fails
- **results/preview_error.png** - Screenshot if an error occurs
- **execution_results.csv** - CSV file containing test results with columns:
  - `file_type` - Type of file tested (e.g., PNG)
  - `file_path` - Path to the uploaded file
  - `preview_detected` - Boolean indicating if preview was detected
  - `status` - Test status (PASS/FAIL)
  - `screenshot` - Path to the captured screenshot

## Example Test Output

```
========== TEST RESULT ==========
PNG file        : /path/to/webApp.png
Preview detected: True
Status          : PASS
Screenshot      : results/preview_pass.png
CSV             : execution_results.csv
```

## Troubleshooting

### Browser Not Found

If you get an error about missing browser binaries:

```bash
playwright install chromium
```

### Timeout Errors

Increase the timeout value:

```bash
python image_preview_test.py --timeout-ms 120000
```

### File Not Found

Ensure the PNG file exists in the script directory or provide the full path:

```bash
python image_preview_test.py --png /full/path/to/image.png
```

### Preview Not Detected

- Check if the web page loads correctly (disable headless mode to see the browser)
- Increase the timeout value
- Verify the target URL is correct

## Contributing

For issues or feature requests, please refer to the Git repository and create an issue or pull request.

## Repository

For the complete Playwright project repository including all scripts and configuration files, please refer to the Git repository link provided in the separate text file.

---

**Last Updated:** May 4, 2026

