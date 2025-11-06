# AstroML-Datasets

**AstroML-Datasets** enables **introductory-level machine learning tasks** across **physics and astronomy** domains. It is designed to help students and early researchers from physics and astrophysics backgrounds explore real-world datasets using basic machine learning techniques.

---

## 🌌 Problem 1: Galaxy Redshift Prediction

This project uses data from the **Sloan Digital Sky Survey (SDSS)** to predict the **redshift of galaxies** from their **photometric magnitudes** across five optical bands — `u`, `g`, `r`, `i`, and `z`.

The dataset, provided in the file **`PhotoZ_SDSS.csv`**, contains several metadata attributes (e.g., right ascension, declination, object identifiers), but only the **photometric magnitudes** are used as input features for this task.
The **target variable** (ground truth) is the **spectroscopic redshift**, representing the true measured redshift of each galaxy.

* **File name:** `PhotoZ_SDSS.csv`
* **Number of samples:** 999,935 galaxies
* **Input features:** Photometric magnitudes in `u`, `g`, `r`, `i`, `z` bands
* **Target variable:** Spectroscopic redshift (`z_spec`)
* **Redshift range:** 1.208629 × 10⁻⁷ – 0.3092074

This task provides an introductory example of how galaxy photometry can be used to estimate redshifts — an essential step in large-scale cosmological analyses.

---

## 🌌 Problem 2: Galaxy Redshift Prediction (HSC • GalaxiesML)

This project uses the **Hyper Suprime-Cam (HSC)** **GalaxiesML** tabular dataset to predict the **redshift of galaxies** from their **photometric magnitudes** across several bands (`g`, `r`, `i`, `z`, `y`, etc.).

The dataset is provided in the file **`photoz_HSC.csv`**, which contains multiple metadata attributes (e.g., object identifiers, coordinates, morphological parameters, and photometric measurements).
Only the **magnitude features** across different bands are used as input features, while the **spectroscopic redshift** serves as the ground truth target.

* **File name:** `photoz_HSC.csv`
* * **Number of samples:** 286,401 galaxies
* **Input features:** Photometric magnitudes across HSC bands (`g`, `r`, `i`, `z`, `y`, etc.)
* **Target variable:** Spectroscopic redshift (`specz_redshift`)
* **Redshift range:** 0.01 – 4


## 📚 Citation

> **GalaxiesML Project**, *HSC GalaxiesML: Hyper Suprime-Cam Photometric and Spectroscopic Galaxy Data*, UCLA DataLab.
> [https://datalab.astro.ucla.edu/galaxiesml.html](https://datalab.astro.ucla.edu/galaxiesml.html)

> **HSC-SSP Collaboration**, *Hyper Suprime-Cam Subaru Strategic Program (HSC-SSP) Data Release*.

> Sloan Digital Sky Survey (SDSS) Collaboration, *SDSS DR17: The Seventeenth Data Release of the Sloan Digital Sky Survey*, Astrophysical Journal Supplement Series, 2022.
> [https://www.sdss.org](https://www.sdss.org)

