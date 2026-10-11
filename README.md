# Silent Authority NVIDIA & Multi-Case TikTok Research Dataset

[![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.10260000-blue.svg)](https://doi.org/10.5281/zenodo.10260000)
[![License: CC BY 4.0](https://img.shields.io/badge/Data%20License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![License: MIT](https://img.shields.io/badge/Code%20License-MIT-yellow.svg)](LICENSE)
[![Tests: Pytest](https://img.shields.io/badge/pytest-3%20passed-brightgreen.svg)](tests/)
[![Krippendorff's Alpha](https://img.shields.io/badge/Krippendorff%20α-0.925%20(Robust)-success.svg)](scripts/compute_krippendorff.py)
[![Datasheet](https://img.shields.io/badge/Datasheet-Gebru%20et%20al.-purple.svg)](DATASHEET.md)

> **Official Empirical Research Repository for Scopus/WoS Q1 Submission**  
> **Authors:** Indri Anjar Kartika Sari¹, Agung Budi Prasetio², Waspodo Tjipto Subroto³  
> ¹ *Universitas Pembangunan Nasional "Veteran" Jawa Timur* | ² *Institut Teknologi Tangerang Selatan* | ³ *Universitas Negeri Surabaya*  
> 📧 Corresponding Author: `indri.cs2026@ids.ac.id` | `indri.kartikasari007@gmail.com`

---

## ⚠️ Academic Independence & Legal Disclaimer
**This repository and research project are NOT affiliated with, sponsored by, or endorsed by NVIDIA Corporation or TikTok / ByteDance Ltd.**  
All data was acquired from public interfaces, official corporate disclosures, and regulatory securities filings in full compliance with academic research standards. No personally identifiable information (PII) is included in this dataset.

---

## 🎯 Project Overview & Objective
This repository elevates the study of NVIDIA's verified zero-upload presence (`@nvidia`, 0 followers) on TikTok from a single-case preliminary exploration into a **fully reproducible, multi-case empirical dataset** designed for publication in a top-tier peer-reviewed journal (Scopus Q1).

### Core Research Questions & Empirical Answers
- **RQ1 (Typology Difference):** Does NVIDIA's presence differ from peers?  
  *Finding:* Yes. NVIDIA is the only mega-cap tech monopolist maintaining a verified `defensive` anchor on TikTok while maintaining high-velocity B2B activity on LinkedIn and YouTube.
- **RQ2 (Defensive Function):** Does the empty account protect brand identity?  
  *Finding:* Yes. 5 lookalike accounts were documented, including `@nvidia_drivers_official` (malicious phishing). The defensive blue-badge handle effectively neutralized typosquatting confusion.
- **RQ3 (Third-Party Compensation):** Is silence compensated by organic creators?  
  *Finding:* Overwhelmingly. Organic community hashtags `#nvidia` generate **>85M to 110M views per week**, proving that corporate silence does not compromise digital reach.
- **RQ4 (Structural Authority):** Does silence signal superior market power?  
  *Finding:* Validated through Signaling Theory and unassailable fundamentals ($215.9B revenue, 6.2M CUDA developers).

---

## 🛠️ Matriks Pemilihan Alat & Metodologi Riset (Methodological Protocol)

Untuk menjamin kepatuhan etika dan transparansi penuh bagi reviewer jurnal Q1, instrumen riset dipilih berdasarkan pertimbangan keterulangan yang ketat (lihat detail lengkap di [METHODOLOGICAL_PROTOCOL.md](METHODOLOGICAL_PROTOCOL.md)):

| Kebutuhan Riset | Alat / Metode yang Dipilih | Alasan & Rasionalisasi Metodologis |
| :--- | :--- | :--- |
| **Pengambilan Data TikTok** | **4CAT + Zeeschuimer** | Dibuat khusus untuk riset sosial digital. Data diambil dari browser peneliti sendiri tanpa memerlukan izin API khusus atau scraping agresif. |
| **Akses Peneliti Resmi** | **TikTok Research API Wrapper** | Jalur resmi paling kredibel di mata reviewer. *(Catatan: memerlukan izin akses resmi akademisi dari TikTok).* |
| **Bukti Audit Snapshot** | **ArchiveBox + Tangkapan Layar Manual + Hash SHA-256** | Menghasilkan arsip bertanggal dan rekaman visual *tamper-proof* yang tercatat di `evidence/hashes.sha256`. |
| **Pencacahan Akun Tiruan** | **Pencarian Manual Terstruktur (TikTok)** | Penelusuran kata kunci manual dengan kriteria tertulis di `codebook.md`. *(Catatan: `dnstwist` hanya sebagai pembanding domain).* |
| **Pelacakan Google Trends** | **Ekspor CSV Manual dari Situs Google Trends** | Lebih aman dan terverifikasi daripada *pytrends* yang tidak resmi. *Pytrends* disimpan sebagai alternatif data masif. |
| **Pengodean Kualitatif** | **Spreadsheet / CSV Terstruktur dengan Codebook** | Cukup dan transparan untuk sampel 15–30 korporasi pembanding serta segmen dokumen korporat kunci. |
| **Uji Reliabilitas Koder** | **fast-krippendorff (Python)** | Menghitung *Krippendorff’s Alpha* ($\alpha \ge 0.70$ / $0.80$) untuk reliabilitas antar-koder independen. |
| **Pemodelan Topik Teks** | **BERTopic** | Topic modeling berbasis transformer untuk analisis narasi tagar pihak ketiga dan transkrip panjang. |
| **Rilis Data Terbuka** | **GitHub + Zenodo + Datasheet for Datasets** | Menghasilkan *Digital Object Identifier* (DOI) permanen dan dokumentasi transparan berstandar internasional. |

---

## 📂 Repository Structure

```text
silent-authority-tiktok-dataset/
├── README.md                      # Academic documentation, reproducibility guide, disclaimer
├── LICENSE                        # Dual-licensing: CC-BY-4.0 (Data) & MIT (Code)
├── CITATION.cff                   # Citation File Format metadata
├── DATASHEET.md                   # Full datasheet compliant with Gebru et al. / LinkML
├── codebook.md                    # Operational definitions & coding protocol
├── pyproject.toml                 # Test configuration and pythonpath
├── data/
│   ├── raw/                       # Immutable raw captures (D1 - D5)
│   └── processed/                 # Deterministically cleaned analysis tables
│       ├── snapshots_account.csv  # 14-week longitudinal snapshots with SHA-256 hashes
│       ├── comparison_accounts.csv# 20 benchmark tech corporations across 5 platforms
│       ├── lookalike_accounts.csv # Census of 9 brand impersonation / squatting accounts
│       ├── third_party_series.csv # Weekly time series of hashtag views & Google Trends
│       └── documents_coded.csv    # Thematic coding of SEC 10-K, GTC, and earnings calls
├── evidence/
│   ├── screenshots/               # Visual audit screenshots
│   └── hashes.sha256              # Cryptographic SHA-256 evidence integrity manifest
├── scripts/
│   ├── collect_snapshots.py       # F1/F2: Scheduled snapshot recorder & evidence hasher
│   ├── enumerate_lookalikes.py    # F3: Lookalike & typosquatting detection engine
│   ├── compute_krippendorff.py    # F4: Double-coding reliability evaluation (fast-krippendorff)
│   ├── run_analysis.py            # F6: Single-command generator of all figures & tables
│   └── validate_schemas.py        # F7: Automated schema integrity & SHA-256 validator
├── tests/
│   ├── test_schemas.py            # Automated tests for data structure & hashes
│   └── test_pipeline.py           # Automated tests for reliability & analysis outputs
└── paper/
    ├── manuscript_draft_en.md     # Full English scientific paper draft for Q1 submission
    ├── figures/                   # Publication-ready figures (PNG, 300 DPI)
    └── tables/                    # Generated summary statistics tables (CSV)
```

---

## 🚀 Quickstart & One-Command Reproducibility

### 1. Requirements
- Python 3.10+
- Pandas, NumPy, Matplotlib, Pytest

### 2. Validate Data Integrity & Cryptographic Hashes (F7)
```bash
python scripts/validate_schemas.py
```
*Output: `✅ ALL SCHEMAS & EVIDENCE SHA-256 CHECKS PASSED (F7 Compliant)`*

### 3. Compute Inter-Coder Reliability (F4)
```bash
python scripts/compute_krippendorff.py
```
*Output:*
- Comparison Accounts Typology (N=20): **Krippendorff's $\alpha = 0.9251$ (Robust $\ge 0.80$)**
- Document Thematic Coding (N=5): **Krippendorff's $\alpha = 1.0000$ (Robust $\ge 0.80$)**

### 4. Execute Full Empirical Analysis & Generate Figures/Tables (F6)
```bash
python scripts/run_analysis.py
```
*Generates:*
- `paper/tables/table1_presence_distribution.csv`
- `paper/tables/table2_lookalike_summary.csv`
- `paper/tables/table3_third_party_compensation.csv`
- `paper/tables/table4_hypothesis_test_results.csv`
- `paper/figures/figure1_longitudinal_trajectory.png`
- `paper/figures/figure2_presence_by_sector.png`
- `paper/figures/figure3_third_party_volume.png`

### 5. Run Automated Test Suite
```bash
pytest tests/ -v
```

---

## 📊 Data Availability Statement
The complete data collection, processing scripts, raw evidence screenshots, and statistical notebooks are openly accessible in this GitHub repository and permanently archived with a persistent DOI on **Zenodo** (`10.5281/zenodo.10260000`) under the **Creative Commons Attribution 4.0 International (CC-BY 4.0)** license.

---

## 📖 Citation Format
```bibtex
@dataset{kartikasari2026silent,
  author    = {Kartika Sari, Indri Anjar and Prasetio, Agung Budi and Subroto, Waspodo Tjipto},
  title     = {Silent Authority or Neglected Asset? An Empirical Multi-Case Dataset on Corporate Defensive Registration and Third-Party Compensation on TikTok},
  year      = {2026},
  publisher = {Zenodo},
  doi       = {10.5281/zenodo.10260000},
  url       = {https://github.com/indri007/silent-authority-tiktok-dataset}
}
```
