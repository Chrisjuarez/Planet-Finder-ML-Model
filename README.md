# Planet Host Propensity — Kepler DR25 (Phase‑1: Data & Preprocess)

Star‑level binary classification: **Does a Kepler star host ≥1 detectable transiting planet?**  
Phase‑1 builds clean **features**, **labels** (strict/lenient), and **train/val/test splits**.



### 2) Put raw Kepler CSVs under `data/raw/kepler`
Expected files (any delimiter works; headers required):
- `kepler_stellar_dr25.csv` — must include: `kepid, teff, logg, feh, radius, mass, kepmag, rrmscdpp03p0, rrmscdpp06p0, rrmscdpp12p0, dataspan, dutycycle, nquarters`
- `kepler_koi_cumulative.csv` — must include: `kepid, koi_disposition`
- `kepler_confirmed_planets.csv` — must include: `kepid`
- *(optional)* `kepler_tce.csv` — must include: `kepid`

> Tip: If your column names differ (e.g., `kic_kepid`, `[Fe/H]`), the pipeline normalizes them.
---

## Repo map
```
planet-host-propensity/
├─ data/ (gitignored)
│  ├─ raw/kepler        # put your CSVs here 
│  └─ processed/  # features/, labels/, splits/
├─ notebooks/
│  ├─ 01_join_labels_clean.ipynb
│  ├─ 02_eda_sanity.ipynb
│  └─ 03_prepare_data_only.ipynb
├─ requirements.txt
└─ README.md
```

