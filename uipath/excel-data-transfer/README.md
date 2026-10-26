# Excel Data Transfer

A UiPath robot that reads a customer data table from one Excel workbook and writes it to another.

## How it works

1. Opens `data\Raw Data 2.xlsx` (`Sheet1`) and reads it into a DataTable. If this fails, a message box shows the error.
2. Opens `data\Sales Data.xlsx` and writes the table to a sheet named `New Data1`, starting at `A1`.

## Run it

**Requirements:** UiPath Studio 23.10 or newer, Windows, Microsoft Excel.

1. Close `Raw Data 2.xlsx` and `Sales Data.xlsx` if they are open in Excel.
2. In Studio, open this folder's `project.json` and let it restore dependencies.
3. Open `Robot_No_1.xaml` and press **Debug File → Run** (F5).

**Expected result:** `data\Sales Data.xlsx` has a new sheet named `New Data1` containing the 6 sample customer rows from `Raw Data 2.xlsx`, starting at cell `A1` with no header row. If reading fails, a message box shows the error.

Sample data in `data\` is synthetic.

## Known limitations

- File paths are relative to the project folder, so run it from the project, not a copied `.xaml` file.
- Headers are not written (`AddHeaders = False`), and there is no check for an empty source sheet.
