# RPA Portfolio

Small UiPath automations covering common back-office tasks: moving spreadsheet data and entering it into web forms.

▶️ **Demo video:** [UiPath RPA Automation for Spreadsheet Form Fill-up](https://youtu.be/he8Nh2y3_TM)

| Project | What it does | Tools |
|---|---|---|
| [Excel → Microsoft Forms](uipath/excel-to-ms-forms) | Submits each Excel row to an MS Forms survey ([demo video](https://youtu.be/he8Nh2y3_TM)) | UiPath, Excel, Edge |
| [Excel Data Transfer](uipath/excel-data-transfer) | Copies a data table between workbooks | UiPath, Excel |

## Getting started

1. Install [UiPath Studio](https://www.uipath.com/product/studio) (the free Community edition works) on Windows, plus Microsoft Excel. The form robot also needs Microsoft Edge.
2. Clone or download this repository.
3. In Studio, choose **Open** and select a project's `project.json` file (for example `uipath/excel-data-transfer/project.json`).
4. If Studio asks, allow it to restore the dependencies (it needs an internet connection the first time).
5. Press **Debug File → Run** (or **F5**). Follow the project's own README for what to check afterwards.

## Notes

- Built with UiPath Studio 23.10; sample data is synthetic.
- Each project has its own README with setup steps, expected results and known limitations.
- Not yet tested in a current Studio version; treat these as working prototypes.

## Tool choice

UiPath fits tasks that go through a user interface (like the form above). 