# Automation Email Workflow

A robust Python-based workflow for automating Excel/CSV data processing and emailing tasks. This project is designed to help you quickly filter, clean, and share tabular data with minimal manual effort.

---

## Overview

This solution enables you to:
- Load data from `.csv`, `.xls`, or `.xlsx` files.
- Clean and normalize data (remove whitespace, fix column names, drop empty rows/columns).
- Filter data based on user-specified conditions.
- Select which columns to keep in the output.
- Export the filtered data to Excel or CSV.
- Email the output file to one or more recipients, with recipient lists managed via YAML or Excel.

---

## Features

- **Automatic Data Loading:** Supports `.csv`, `.xls`, and `.xlsx` files.
- **Data Cleaning:** Strips whitespace, normalizes text, and removes empty rows/columns.
- **Flexible Filtering:** Filter data based on user-specified conditions.
- **Column Selection:** Choose which columns to retain in the output.
- **Output Export:** Save filtered data to Excel or CSV.
- **Automated Emailing:** Send the output file as an email attachment to one or more recipients.
- **Configurable Recipients:** Load email addresses from a YAML file or Excel file.

---

## Requirements

- Python 3.7 or higher
- The following Python packages:
  - `pandas`
  - `pyyaml`
  - `openpyxl`

Install dependencies using:

```bash
pip install -r requirements.txt
```

---

## File Structure

- `automation_final.ipynb` — Main Jupyter notebook with all logic and documentation.
- `Mall_Customers.csv` — Sample input data file.
- `email.yaml` — YAML file listing email recipients.
- `requirements.txt` — Python dependencies.
- `README.md` — Project documentation.

---

## Configuration

### Email Recipients

Preferred:  
Edit `email.yaml` to specify recipient addresses:

```yaml
emails:
  - user1@example.com
  - user2@example.com
```

Fallback:  
If `email.yaml` is missing, place an `email_ids.xlsx` file in the project directory with a column containing email addresses (column name should include "email").

---

## Usage

1. **Open the Notebook:**  
   Launch `automation_final.ipynb` in Jupyter or VS Code.

2. **Install Dependencies:**  
   Run the first three code cells to install required packages.

3. **Run the Workflow:**  
   Execute the notebook cells sequentially.  
   - The script will prompt for:
     - Column to filter by
     - Operator (`==`, `!=`, `>`, `>=`, `<`, `<=`)
     - Value to compare
     - Columns to keep (comma-separated)
     - Whether to email the output

4. **Emailing Output:**  
   - If emailing, you will be prompted for your Gmail address and an [App Password](https://support.google.com/accounts/answer/185833).
   - Select recipients from the loaded list or enter manually.

---

## Security Note

- **Gmail App Password:**  
  For Gmail, enable 2FA and use an App Password instead of your main password for SMTP access.

---

## Customization

- **Input File:**  
  Change the `file_path` variable in the notebook to process a different file.
- **Output File:**  
  The filtered data is saved as `filtered_output.xlsx` by default.

---

## Troubleshooting

- **File Not Found:**  
  Ensure your input files are in the project directory.
- **Email Issues:**  
  - Check your App Password and Gmail security settings.
  - Ensure less secure app access is enabled if not using App Passwords (not recommended).

---

## License

This project is provided for educational and internal automation purposes.

---
