# sanitize-csv-files-extension

## About
CSV injection occurs which occurs when an attacker injects malicious code into a CSV file, and this code is executed when the file is opened in a spreadsheet program.
This type of attack is possible because most spreadsheet programs have a set of built-in functions that run automatically when a CSV file is opened with the spreadsheet program.
Given the widespread usage of CSV files and programs that interpret those CSV files, the risk posed by such CSV injection attacks is great.

In this repository, I present a browser extension designed to sanitize all downloaded CSV files by eliminating any harmful code while preserving the integrity of benign code.
The extension does this by first finding all formulas within a CSV file, and determining whether or not each one has the potential to contain malicious code.
If the extension determines that a formula may be malicious, it will edit the cell containing that formula so that spreadsheet programs will interpret the cell as text, and will not execute it.

## How to Run
To run this extension, do the following steps:

1. Build the runtime folder. If you're on Linux or MacOS, run `cd runtime; source setup.sh`, and if you're on Windows, run `cd runtime; python setup.py`.

2. Download the folder "extension".

3. Open the Chrome web browser and go to chrome://extensions.

4. Toggle "Developer Mode" on (the switch is located at the top-right corner of the page).

5. Click "Load unpacked" and select the "extension" folder you downloaded in step 1. The extension should load.

See https://medium.com/pythoniq/write-chrome-extensions-in-python-6c6b0e2e1573 for more information.

## Credits
The skeleton code for this Chrome extension was taken from [PFython/pyscript-local-runtime](https://github.com/PFython/pyscript-local-runtime).
Additionally, I referenced https://www.jhanley.com/blog/pyscript-files-and-file-systems-part-1/ and https://pyscript.recipes/2023.05.1/basic/file-download/ while working on this extension.
