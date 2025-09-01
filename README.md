# Harvest Reporter

This script prepares monthly or date-range based service reports for clients using time tracking data from the Harvest API. The reports are generated as Excel files in German.

## Features

- Generates Excel reports with time entries.
- Report columns: "Datum", "Leistung", "Arbeitsstunden".
- Calculates the total hours using an Excel formula.
- Report sheet is named "Remote".
- Filename pattern: `Leistungsuuebersicht [client name] [month] [year].xlsx` or `Leistungsuuebersicht [client name] [from_date]_to_[to_date].xlsx`.
- Can be run for the previous month or for a specific date range using command-line arguments.

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

### Generating a report for the previous month

Run the script without any arguments:

```bash
/Users/rreimche/dev/harvest-reporter/venv/bin/python /Users/rreimche/dev/harvest-reporter/reporter.py
```

### Generating a report for a specific date range

You can use the optional `--from_date` and `--to_date` arguments to generate a report for a specific period. The date format is `YYYY-MM-DD`.

```bash
/Users/rreimche/dev/harvest-reporter/venv/bin/python /Users/rreimche/dev/harvest-reporter/reporter.py --from_date 2025-07-01 --to_date 2025-07-31
```