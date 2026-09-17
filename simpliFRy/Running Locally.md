1. Delete the venv folder from the directory using `cd..` followed by `Remove-Item -Recurse -Force .venv`
2. Install python 3.11 or 3.12 (using `py install 3.11`) --> ensure no virtual environments are open
3. Check python versions using `py -0p`
4. Create a virtual environment with python 3.11 or 3.12 using `py -3.11 -m venv .venv`
5. Activate the virtual environment using .\.venv\Scripts\Activate.ps1
6. Change to the simpliFRy folder using `cd simplifry`
7. Run `pip install -r requirements.txt` to download the dependencies (takes awhile)
8. If the previous line generates error messages with "error: Microsoft Visual C++ 14.0 or greater is required. Get it with "Microsoft C++ Build Tools": https://visualstudio.microsoft.com/visual-cpp-build-tools/", go and download. After downloading, select Desktop development with C++ and ensure the following defaults components are checked in the Installation details panel on the right side:
- MSVC v143 - VS 2022 C++ x64/x86 build tools (or v142 depending on installer version).
- Windows 10 SDK or Windows 11 SDK.
- C++ CMake tools for Windows (recommended).
9. Kill your terminal in VS code and reopen it (check for venv prefix)
10. Run `pip install -- upgrade setuptools wheel`
- Add wheels.exe to PATH (optional): Search for environment variables --> path --> edit --> paste the URL from the terminal prompt
11. Rerun `pip install -r requirements.txt`
12. `Run py app.py`
13. When the line below displays in the terminal, go to http://localhost:1333/ to access the program 
- "Serving Flask app 'app'
- * Debug mode: on
14. Run the following command from the simpliFRy directory to clean up older log files
- `Get-ChildItem .\data\logs\ -Filter *.logs | Where-Object { $_.LastWriteTime -lt (Get-Date).AddDays(-7) } | Remove-Item`

**VERY IMPORTANT NOTE: This takes quite a lot of storage. Ensure the folder is saved in the hard disk and not in OneDrive. The terminal should point to a path like this C:\Dev\Fusion-FRS-3 with nothing related to OneDrive.**