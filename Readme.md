# AutoSheets (SheetMultiplication)

Create multiple Revit® sheets from a master template: copy titleblocks and parameters, replicate legends, place views (auto‑duplicate if already placed), and import/export data via Excel.

## Short description
AutoSheets automates repetitive sheet production in Autodesk® Revit®. Create dozens or hundreds of sheets from a selected template in one operation, with unit‑aware offsets, Excel import/export and robust validation and logging.

## Features
- Duplicate a chosen master sheet (titleblock, sheet parameters and legends)  
- Place project views on new sheets; automatically duplicate views already placed elsewhere  
- Precise X/Y offsets (metric mm or imperial ft‑in) with preview  
- Bulk import/export using XLSX (Number, Name, ViewName, OffsetX, OffsetY)  
- Validation: empty/duplicate sheet numbers, existing sheet numbers in project, missing/duplicate views, missing master sheet  
- Detailed results dialog and logs for failed operations

Typical install (Autodesk Apps Framework):
- Installer places the add‑in bundle into:
  `C:\ProgramData\Autodesk\ApplicationPlugins\AutoSheets.bundle`
- Restart Revit. Launch from the Add‑Ins ribbon (AutoSheets).

Uninstall:
- Use Autodesk App Store uninstall or Windows __Settings > Apps & features__ to remove the product entry.
- Or close Revit and delete the bundle folder from:
  `C:\ProgramData\Autodesk\ApplicationPlugins\AutoSheets.bundle`
- Manually Remove any per‑user files from `%APPDATA%\AutoSheets` if present, then restart Revit.

## Usage (workflow)
1. Open project in Revit and run AutoSheets from the Add‑Ins ribbon.  
2. Select a master (template) sheet from your project. The titleblock and legends will be used.  
3. Add rows manually or Import from Excel (XLSX). Required columns: `Sheet number`, `Sheet name`, `View name`, `Offset X`, `Offset Y`.  
4. Choose unit type for offsets (Metric mm or Imperial ft‑in). Enter offsets and preview placement.  
5. Run validation and fix any highlighted issues.  
6. Click Create — AutoSheets duplicates the template, copies titleblock parameters, replicates legends and places views. Review results dialog for created/failed items.

## Excel format (XLSX)
Columns (case‑insensitive):
- `Sheet number` — sheet number (required)  
- `Sheet name` — sheet name (required)  
- `View name` — exact view name from the project (leave blank for no view)  
- `Offset X` — optional; unit interpretation depends on selected unit type  
- `Offset Y` — optional

Example row:
`100`, `Ground Floor Plan`, `GF - Plan`, `0'-0"`, `0'-4"`

Notes:
- Use XLSX (Excel native). Avoid CSV with ambiguous encodings.
- For imperial offsets use typical ft‑in or decimal ft as supported by the UI converter.

## Supported Revit / Build
- Compiled for .NET Framework 4.8 (C# 7.3). Ensure the bundle is installed into the matching Revit year add‑ins folder.

## Logging & diagnostics
- AutoSheets writes Info and Error logs. When reporting issues include: Revit version, AutoSheets version (About dialog), a minimal RVT demonstrating the problem, the Excel sample and logs.

## Support
- Report issues and feature requests on GitHub Issues:
  https://github.com/HikeByteStudio/AutoSheets/issues
- For direct support email (replace with your contact): `hikebyte.it@gmail.com`
- When opening an issue, include Revit version, AutoSheets version, steps to reproduce and relevant files.

## Known issues
- Excel import may fail on non‑XLSX or incorrectly encoded files — use Excel saved XLSX and UTF‑8 if needed.  
- Identical view names cause ambiguity — prefer unique view names or manual assignment.  
- Complex titleblocks or nested families may cause parameter copy issues; failures are logged.  
- Very large batches can be slow or memory‑intensive — back up your project before large operations.  
- Workshared projects: perform operations following your central/local workflow (work on a local copy or coordinate with your BIM manager).

## Privacy Policy

AutoSheets does not collect, store, or transmit any personal data.
The application operates entirely within Autodesk® Revit® and processes data locally on the user's machine. No user data is sent to external servers, services, or third parties.
AutoSheets does not use analytics tools, tracking mechanisms, or third-party SDKs.
All data handled by the application (such as sheet names, numbers, and view assignments) remains within the Revit project environment.

### Data Sharing
AutoSheets does not share any data with third parties.

### Data Retention
Since no data is collected or stored externally, no data retention applies.

### User Control
As no personal data is collected, no action is required to revoke consent or request deletion.

If you have any questions regarding this policy, please contact:
hikebyte.it@gmail.com

---
