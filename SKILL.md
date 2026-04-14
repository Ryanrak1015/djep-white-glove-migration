# DJEP CRM Migration (HoneyBook / Check Cherry)

## Description
This skill provides the exact workflow and field mapping required to migrate client and contact data from other CRMs (like HoneyBook or Check Cherry) into DJ Event Planner (DJEP). This is typically sold as a "White-Glove Migration" add-on service by DJEPSetup.com.

## Prerequisites
- Access to the client's source CRM (HoneyBook, Check Cherry, etc.) to export data
- Access to the client's DJEP account (Master Administrator level)
- A spreadsheet editor (Excel, Google Sheets, or Python/Pandas) to clean and map the CSV data

## Important Limitations & Policies
1. **Static Data Only:** Only Clients, Contacts, Venues, and Equipment can be imported via CSV.
2. **No Workflows:** Past event history, signed contracts, payment records, email sequences, and packages **cannot** be imported. They must be rebuilt natively in DJEP.
3. **Anti-Spam Policy:** DJEP strictly prohibits importing cold lead lists for mass emailing. Only existing clients with a prior relationship can be imported and emailed through the platform.

## Step-by-Step Migration Workflow

### Step 1: Export Data from Source CRM
1. Log into the client's HoneyBook or Check Cherry account.
2. Navigate to the Contacts or Clients section.
3. Export the full list as a CSV file.

### Step 2: Clean and Map the CSV
Open the exported CSV and rename the column headers to match DJEP's exact import fields. Delete any columns that do not map to a DJEP field.

**DJEP Client Import Fields:**
`First Name`, `Last Name`, `Organization`, `Name Prefix`, `Name Suffix`, `Middle Name`, `Home Phone`, `Work Phone`, `Cell Phone`, `Fax Phone`, `Email`, `Website`, `Address`, `Address 2`, `City`, `State`, `Zipcode`, `Country`, `Notes`, `Birthday`, `Customer Number`, `Client Type`, `Wedding Anniversary`

**DJEP Contact Import Fields:**
`First Name`, `Middle Name`, `Last Name`, `Category`, `Company`, `Job Title`, `Business Address`, `Business City`, `Business State`, `Business Postal Code`, `Business Country`, `Business Fax`, `Business Phone`, `Home Address`, `Home City`, `Home State`, `Home Postal Code`, `Home Country`, `Home Fax`, `Mobile Phone`, `Pager`, `Anniversary`, `Birthday`, `Email Address`, `Notes`, `Web Page`, `Spouse`, `Date Added`

*Note: Dates must be formatted as MM/DD/YYYY.*

### Step 3: Import into DJEP
1. Log into the client's DJEP account.
2. Navigate to **Setup** (left sidebar).
3. Click on **Import Data** (or navigate directly to `setup.asp?action=show_import_options`).
4. Select either **CLIENTS** or **CONTACTS** depending on the list type.
5. Click **Select File...** and upload the cleaned CSV.
6. DJEP will present a mapping screen. Verify that your CSV headers correctly map to the DJEP database fields.
7. Execute the import and verify the records in the Contact Manager.

## Troubleshooting
- **Date Errors:** If dates fail to import, ensure they are strictly in `MM/DD/YYYY` format in the CSV before uploading.
- **Missing Fields:** If a source CRM has custom data that doesn't fit standard DJEP fields, map it to one of DJEP's `Custom Client Field 1-20` or append it to the `Notes` field.
