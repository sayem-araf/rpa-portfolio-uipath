# Excel → Microsoft Forms

A UiPath robot that reads rows from an Excel workbook and submits each row to a Microsoft Forms survey, replacing repetitive manual data entry.

**Demo video:** [UiPath RPA Automation for Spreadsheet Form Fill-up](https://youtu.be/he8Nh2y3_TM)

## How it works

1. Opens `data\Raw Data 1.xlsx` (`Sheet1`) and reads it into a DataTable (headers included).
2. For each row, opens the form in Edge.
3. Types the first 9 columns into the form's fields, clicks **Submit**, and closes the tab.
4. Any error is caught and written to the log instead of stopping the robot silently.

**Why RPA:** the form has no import option and is filled through its web UI, which is where UI automation fits.

## Run it

**Requirements:** UiPath Studio 23.10 or newer, Windows, Microsoft Excel, Microsoft Edge, and the UiPath browser extension for Edge (Studio: **Tools → UiPath Extensions → Edge**).

1. Create your own test Microsoft Form with 9 text questions, in the same order as the spreadsheet columns, and copy its link.
2. In Studio, open this folder's `project.json` and let it restore dependencies.
3. Open `Robot_No_2.xaml`, select the **Open Browser** activity and replace the placeholder URL with your form link (see below).
4. Close `data\Raw Data 1.xlsx` if it is open, then press **Debug File → Run** (F5).

**Expected result:** Edge opens your form once per row, the 9 fields are filled with the row's values, and the tab closes. The 3 sample rows should produce 3 responses in your form's results. Errors are written to the log.

Sample input in `data\` is synthetic. Keep the layout: 9 columns, one record per row.

## Before you run: use your own form

`Robot_No_2.xaml` contains the placeholder `https://forms.office.com/YOUR-FORM-LINK-HERE`. Replace it with your own form's link in the **Open Browser** activity, and make sure the form has 9 text questions in the same order as the spreadsheet columns. Don't run this against someone else's form.

## Known limitations

- Field selectors are tied to the original form's layout; a different form needs the selectors re-recorded in UiPath.
- No input validation (empty rows, wrong column count) and no retry logic yet.
- The form URL is hard-coded rather than configurable.
