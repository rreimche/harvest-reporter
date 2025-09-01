# Harvest Reporter

This script prepares reports for services for my clients every month. It uses the harvest REST API to get data and prepare reports. The reports are generated in German.

## File Structure

- `reporter.py`: The main script.
- `config.ini`: Configuration file for API credentials and client IDs.
- `requirements.txt`: Python dependencies.
- `GEMINI.md`: This file.
- `venv/`: Python virtual environment.
- `.gitignore`: Git ignore file.

## Setup

1.  **Install Dependencies:**

    ```bash
    python3 -m venv venv
    venv/bin/python -m pip install -r requirements.txt
    ```

2.  **Configure the script:**

    Copy the `config.ini.example` to `config.ini` and fill in your Harvest API token, account ID, and client IDs.

    ```ini
    [harvest]
    token = YOUR_HARVEST_API_TOKEN
    account_id = YOUR_HARVEST_ACCOUNT_ID

    [clients]
    # Comma-separated list of client IDs to generate reports for
    ids = 12345, 67890
    ```

## Usage

Run the script from your terminal:

```bash
/Users/rreimche/dev/harvest-reporter/venv/bin/python /Users/rreimche/dev/harvest-reporter/reporter.py
```

The script will generate an Excel report for each client for the previous month.
