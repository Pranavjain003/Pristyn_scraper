# 🩺 Doctor Profile Scraper — Pristyn Care

This project scrapes detailed information about doctors listed on the [Pristyn Care](https://www.pristyncare.com) website. It uses a CSV of treatment names (from the homepage) to find all associated doctors, then scrapes each doctor’s profile while avoiding duplicates.

---

## 📁 Project Structure

```
├── doctors_by_treatment.csv          # Contains treatments and associated doctor profile URLs
├── unique_scraped_doctor_profiles.csv # Output file with detailed doctor information (deduplicated)
├── code.ipynb                        # Main scraping script (Jupyter Notebook)
└── README.md                         # This file
```

---

## 🚀 How It Works

1. **Input CSV**  
   - You start with a CSV (`doctors_by_treatment.csv`) containing treatments and doctor profile URLs.

2. **Scraping Logic**  
   - The script opens each URL.
   - It scrapes the doctor’s name, about section, medical registration, education, and list of treatments.
   - Duplicates are avoided based on both doctor name and URL.

3. **Output CSV**  
   - A final file `unique_scraped_doctor_profiles.csv` is created containing only **unique** doctor profiles.

---

## 🛠️ Requirements

Install the required Python libraries using:

```bash
pip install requests beautifulsoup4 pandas
```

---

## 📌 Usage

Run the Jupyter Notebook (`code.ipynb`) or convert it to a Python file (`.py`) and run:

```bash
python code.py
```

---

## 📝 Output Columns

The final CSV includes the following:

- `name`
- `about`
- `registration`
- `education` (comma-separated list)
- `treatments` (comma-separated list)
- `url`

---

## 💡 Notes

- The scraper avoids scraping the same doctor multiple times.
- A short delay (`1.5s`) is added between requests to avoid server overload.
- If a profile has missing fields, it still gets included with `None` or empty values.