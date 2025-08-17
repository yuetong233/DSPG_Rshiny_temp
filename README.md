# R Shiny Project Template

This repository provides a reproducible template for developing and deploying an **R Shiny** application.  
It separates scripts, raw data, cleaned data, and the Shiny app itself for clarity and reproducibility.

---

## 📂 Project Structure

```
shiny-template/
├─ README.md              # Project documentation
├─ .gitignore             # Files ignored by Git
├─ scripts/               # Data pipeline scripts
│  ├─ 01_download.R
│  ├─ 02_clean.R
│  └─ 03_analysis.R
├─ data/
│  ├─ raw/                # Immutable input data (not committed if large/private)
│  └─ cleaned/            # Processed outputs from scripts
├─ shiny/                 # Shiny application
│  ├─ app.R
│  ├─ global.R
│  └─ www/                # Static assets (CSS, JS, images)
└─ .github/workflows/     # Optional CI (linting, checks)
```

---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/shiny-template.git
cd shiny-template
```

### 2. Install Dependencies
In R, initialize `renv` and install core packages:
```r
install.packages("renv")
renv::init()

# Install essential packages
install.packages(c("shiny", "bslib", "readr", "dplyr", "leaflet", "DT"))
renv::snapshot()
```

### 3. Add Your Data
- Place **raw input data** in `data/raw/` (small, non-sensitive only).  
- Run scripts in `scripts/` to process data into `data/cleaned/`.  

### 4. Run the Shiny App
```r
shiny::runApp("shiny")
```

---

## 📦 Deployment

### shinyapps.io
```r
install.packages("rsconnect")
rsconnect::setAccountInfo(name = "...", token = "...", secret = "...")
rsconnect::deployApp("shiny")
```

### Shiny Server
Copy the `shiny/` folder to your server and configure accordingly.  

---

## 📝 Contributing

- Fork this repository  
- Create a new branch (`git checkout -b feature-new`)  
- Commit your changes (`git commit -m "Add new feature"`)  
- Push to the branch (`git push origin feature-new`)  
- Open a Pull Request  

---

## 📄 License
MIT License – feel free to use, modify, and share.

---

## ⚠️ Notes

- Do **not** commit large or private data to GitHub.  
- Use `.gitignore` to exclude sensitive files.  
- Document how raw data can be obtained in `README_data.md` if applicable.
