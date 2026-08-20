# Data Cleaning and Data Validation

## Overview

This project demonstrates the importance of data cleaning and validation using an employee purchase request dataset. The objective is to identify data inconsistencies, correct errors, standardise formatting, 
and apply validation rules to improve data quality and ensure accurate future data entry.

## Dataset

The dataset contains 286 records. 

The dataset includes the following fields:

* Request ID
* Request Date
* Employee Name
* Department
* Request Type
* Vendor
* Payment Method
* Estimated Cost
* Quantity
* Urgency
* Approval Status

## Tools and Techniques

The project was completed using **Microsoft Excel** and consists of two worksheets:

* **Raw Data:** Contains the original dataset, including highlighted errors and cell notes explaining the identified issues and how they can be corrected.
* **Cleaned Data:** Contains the cleaned, validated, and formatted dataset.

The following Excel tools and techniques were used:

* Conditional Formatting
* Data Validation
* Data Cleaning
* Custom Data Validation Error Alerts
* Table Formatting
* Data Validation Using Custom Formulas

## Procedure

### 1. Identifying Inconsistent Request IDs

To identify inconsistent values in the **Request ID** column:

1. Highlight the entire **Request ID** column.
2. Navigate to the **Home** tab and select **Conditional Formatting**.
3. Select **New Rule**.
4. Choose the option to format cells containing values that do not include the hyphen (`-`), as the inconsistent Request IDs were missing this character.
5. Select a formatting style and apply the rule.

The inconsistent Request IDs will then be highlighted using the selected format.

### 2. Correcting Request Date Formatting

Some values in the **Request Date** column were left-aligned, indicating that Excel was treating them as text rather than dates.

To correct this:

1. Select the **Request Date** column using `Ctrl + Shift + Page Down`.
2. Navigate to the **Data** tab and select **Text to Columns**.
3. Click **Next** twice in the Text to Columns Wizard.
4. Under **Column Data Format**, select **Date**.
5. Choose the required date format.
6. Click **Finish**.

The text values will be converted into properly formatted Excel dates.

### 3. Correcting Request Type Spelling Errors

The **Request Type** column contained spelling inconsistencies. Data Validation was used to standardise the available values.

1. Highlight the entire **Request Type** column.

2. Navigate to the **Data** tab and select **Data Validation**.

3. Under **Settings**, select **List** from the **Allow** drop-down menu.

4. Enter the approved values:

   * Hardware
   * Software
   * Office Supplies
   * Services

5. Apply the validation rule.

6. From the **Data** tab, select **Circle Invalid Data** to identify entries that do not match the approved list.

7. Review the circled values and select the correct option from the validation list.

The red circle automatically disappears once a valid value is selected.

### 4. Converting Estimated Cost Values to Numbers

In the **Estimated Cost** column, some values were left-aligned while others were right-aligned. This indicated that some numerical values were being stored as text.

To identify and correct these values:

1. Create a new column next to **Estimated Cost**.
2. Use the `=ISNUMBER()` function, referencing the first cell in the Estimated Cost column.
3. Copy the formula down the entire column using `Ctrl + Shift + Page Down`.
4. Values returning **TRUE** are recognised as numbers, while values returning **FALSE** are stored as text.
5. Use **Conditional Formatting** to highlight cells containing `FALSE`.
6. Enter `1.00` in an empty cell immediately below the Estimated Cost data and copy the cell.
7. Highlight the entire **Estimated Cost** column.
8. Navigate to **Paste Special** under the **Home** tab and select **Multiply**.

This converts text-formatted numerical values into recognised numerical values. The values will then be right-aligned, indicating that Excel recognises them as numbers.

### 5. Creating a Dynamic Table and Applying Data Validation

Before applying additional validation rules, the dataset was converted into an Excel table to ensure that the data remains structured and dynamic.

Data validation was then applied to numerical columns:

1. Highlight the relevant numerical column.
2. Navigate to the **Data** tab and select **Data Validation**.
3. Under **Allow**, select **Whole Number**.
4. Define the appropriate minimum and maximum values.

This ensures that future entries outside the specified range or incorrect data format are rejected, helping maintain data consistency and quality.
