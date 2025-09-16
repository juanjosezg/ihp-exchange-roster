# IHP Roster File Conversion Script

This script processes and formats IHP roster files to ensure phone numbers are standardized and data is categorized. 
Follow these steps to prepare the files in the correct format for import.

## Prerequisites
- Python 3.x installed on your machine
- Required libraries: pandas, os, and re

## Setup
1. Place your IHP roster files (in CSV format) in the `client_files/` directory. Make sure each CSV file has a column called `phone` containing unformatted phone numbers.

2. The script will automatically read each CSV file in `client_files/`, format the phone numbers, categorize the data by type of provider, and save the results in a new directory called `ready_for_import/`.

## Usage

1. **Run the Script**

    Simply run the script in a Python environment. The script will:
    - Read all CSV files from `client_files/`
    - Format phone numbers to the `(XXX) XXX-XXXX` format
    - Filter data into three categories: providers, hospitals, and facilities
    - Rename and reorder columns for consistency
    - Save the processed files in `ready_for_import/` with appropriate filenames

2. **File Organization**

    Each processed file will be named according to its category (e.g., `providers_file.csv`, `hospitals_file.csv`, etc.). This makes it easy to distinguish and use the files as needed.

## Column Renaming

The script automatically renames specific columns in each CSV file to ensure consistency. Here’s the column mapping:
- `first_name` -> `firstname`
- `last_name` -> `lastname`
- `specialty` -> `specialty`
- `clinic_name` -> `hospitalname`
- `phone` -> `phone` (formatted)
- `address1` -> `address`
- `address2` -> `address2`
- `city` -> `city`
- `state` -> `state`
- `zip` -> `zipcode`
- `county` -> `county`
- `accepting` -> `acceptingnewpatients`

## Example Output

After running the script, you will see output files in the `ready_for_import/` folder. For example:

```
ready_for_import/providers_<original_filename>.csv
ready_for_import/hospitals_<original_filename>.csv
ready_for_import/facilities_<original_filename>.csv
```

Each of these files contains the formatted and filtered data for each respective category.

## Notes
- Phone numbers must be in the `phone` column and contain 10-digit numbers to be properly formatted.
- Ensure the `type_of_provider` column exists and contains values to correctly categorize entries (e.g., 'SPECIALIST', 'HOSPITAL').

## Troubleshooting

If the phone numbers are not formatting correctly:
- Ensure they are 10-digit numbers without special characters.
- Verify that all columns are named correctly.


