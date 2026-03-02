# DAVO — Directional Analysis & Visualization Operations

> A professional desktop utility for MWD and directional drilling — PDF timestamp annotation, ECD calculations, and more.

---

## ⬇️ Download

Head to the [**Releases**](https://github.com/dn3ndra/DAVO-Utility/releases/latest) page and download the latest `DAVO.exe`.

No installation required — just run the `.exe`.

---

## ✨ Features

- **📄 PDF Timestamp Annotation** — Automatically annotate directional survey PDFs with timestamps from a CSV or Excel file, using direct matching and interpolation
- **💡 ECD Calculator** — Single and batch Equivalent Circulating Density calculations with results in ppg, SG, kPa/m, and bar
- **📊 ECD Chart Visualization** — Interactive depth vs ECD charts rendered from batch data
- **🗂️ Drag & Drop** — Drop PDF and data files directly into the app
- **🔄 Auto-Update** — The app checks for new versions on startup and can update itself automatically
- **🎨 Dark / Light Theme** — Switch themes from the Settings menu

---

## 🚀 Getting Started

### 1. Download & Run
Download `DAVO.exe` from [Releases](https://github.com/dn3ndra/DAVO-Utility/releases/latest) and double-click to launch.

### 2. Time Report Tab (PDF Annotation)
1. Drop or browse for one or more **PDF** drilling reports
2. Drop or browse for a **CSV or XLSX** timestamp file
   - Must contain a **depth column** (e.g. `MDEPTH`, `MD`, `Depth`)
   - Must contain a **time column** (e.g. `Timestamp`, `Time`, `DateTime`)
3. Set your **interval** (e.g. every 10m or 25ft) and **unit**
4. Optionally set an **X-offset** to fine-tune annotation placement
5. Optionally specify **pages to skip** (e.g. `1,3` to skip title pages)
6. Click **▶ Process** — annotated PDFs are saved alongside the originals (or to a custom output folder)

### 3. ECD Calculator Tab
**Single calculation:**
- Enter annular pressure (psi), TVD, and optional mud weight (ppg)
- Click **Calculate ECD** — results appear instantly in ppg, SG, kPa/m, and bar

**Batch processing:**
- Click **📂 Load File** and select a CSV or XLSX with pressure and TVD columns
- Results are appended as new columns and saved to an Excel file
- Click **📈 Chart** to visualize ECD vs depth

---

## 📁 Timestamp File Format

Your CSV or Excel file needs at minimum two columns. Column names are detected automatically — no exact naming required.

| MDEPTH | Timestamp |
|--------|-----------|
| 1000 | 2024-01-15 08:00 |
| 1010 | 2024-01-15 08:14 |
| 1020 | 2024-01-15 08:31 |

Supported depth column names: `MDEPTH`, `MD`, `Depth`, `MeasuredDepth`  
Supported time column names: `Timestamp`, `Time`, `DateTime`, `Date`

---

## 📁 ECD Batch File Format

| P_Annular | TVD | MudWeight |
|-----------|-----|-----------|
| 450 | 1500 | 10.2 |
| 520 | 1600 | 10.2 |

Supported pressure column names: `P_Annular`, `AnnularPressure`, `Annular`, `Pressure`  
Supported TVD column names: `TVD`, `TrueVerticalDepth`, `VerticalDepth`, `Depth`  
Mud weight column is optional.

---

## ⚙️ Settings

Access via the **⚙ Settings** menu in the top bar:
- Toggle **Dark / Light** theme
- All settings are saved automatically between sessions

---

## 🔄 Auto-Update

DAVO checks for updates 2 seconds after launch. If a new version is available, a popup will appear with release notes and a one-click install button. The updater downloads the new `.exe`, replaces the old one, and relaunches automatically.

To disable update checks, set the environment variable `DAVO_DEV=1` before launching.

---

## 🛠️ Building from Source

**Requirements:**
- Python 3.9+
- PyInstaller

**Install dependencies:**
```bash
pip install pyinstaller PyQt5 pymupdf pandas openpyxl pillow matplotlib
```

**Build:**
```bash
pyinstaller --noconfirm DAVO.spec
```

The compiled `.exe` will be in the `dist/` folder.

---

## 📋 Requirements (for running from source)

```
PyQt5
pymupdf (fitz)
pandas
openpyxl
Pillow
matplotlib
```

---

## 📝 Logs

A log file is written to:
```
C:\Users\<YourName>\davo_log.txt
```

Check this file if you encounter any issues.

---

## 👤 Author

**Dhanendra N.**  
[github.com/dn3ndra](https://github.com/dn3ndra)

---

## 📄 License

This project is proprietary software. All rights reserved.
