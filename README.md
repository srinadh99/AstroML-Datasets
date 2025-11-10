# AstroML-Datasets
## More to be uploaded!
## A unified benchmark of 100 Physics & Astronomy datasets.

**AstroML-Datasets** enables **introductory-level machine learning tasks** across **physics and astronomy** domains. It is designed to help students and early researchers from physics and astrophysics backgrounds explore real-world datasets using basic machine learning techniques.

---

## 🌌 1: Galaxy Redshift Prediction

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

## 🌌 2: Galaxy Redshift Prediction (HSC • GalaxiesML)

This project uses the **Hyper Suprime-Cam (HSC)** **GalaxiesML** tabular dataset to predict the **redshift of galaxies** from their **photometric magnitudes** across several bands (`g`, `r`, `i`, `z`, `y`, etc.).

The dataset is provided in the file **`photoz_HSC.csv`**, which contains multiple metadata attributes (e.g., object identifiers, coordinates, morphological parameters, and photometric measurements).
Only the **magnitude features** across different bands are used as input features, while the **spectroscopic redshift** serves as the ground truth target.

* **File name:** `photoz_HSC.csv`
* * **Number of samples:** 286,401 galaxies
* **Input features:** Photometric magnitudes across HSC bands (`g`, `r`, `i`, `z`, `y`, etc.)
* **Target variable:** Spectroscopic redshift (`specz_redshift`)
* **Redshift range:** 0.01 – 4

---

## 🌠 Problem 3: Star–Galaxy–Quasar Classification (SDSS)

This project uses data from the **Sloan Digital Sky Survey (SDSS)** to classify astronomical sources as **stars**, **galaxies**, and **quasars** based on their **photometric properties**.
The dataset includes **24 photometric features** derived from dereddened magnitudes, colors, and profile-based measurements across the five SDSS bands (`u`, `g`, `r`, `i`, `z`).

The data are provided in the following files:

* **`dnnx_sg.npy`**, **`y_sg.npy`** — Used for **star–galaxy** binary classification

* **`dnnx_sgq.npy`**, **`y_sgq.npy`** — Used for **star–galaxy–quasar** three-class classification

* **`objlist.npy`** — Contains the **SDSS Object IDs** for all sources

* **Total sources:** 239,999

  * Stars: 80,000 Galaxies: 79,999 Quasars: 80,000

This dataset enables both binary and multi-class classification tasks, offering an introductory example of applying supervised learning to astronomical source separation.

---

## ⚡ Problem 4: Gamma / Hadron Event Classification (UCI • MAGIC Gamma Telescope)

This project focuses on classifying **atmospheric particle events** detected by a ground-based **Cherenkov gamma-ray telescope** as either **gamma-ray (signal)** or **hadronic (background)** in origin.
The task demonstrates how supervised machine learning can be applied to **astroparticle physics** problems, where distinguishing rare astrophysical gamma events from the abundant hadronic background is essential for high-energy gamma-ray astronomy.

---

### 📊 About Dataset

The data, provided as a **`magic04_gamma.csv` file** from the **UCI Machine Learning Repository**, are **computer-generated simulations** that reproduce the detection of high-energy gamma particles using a **MAGIC-type atmospheric Cherenkov telescope**.

These telescopes detect gamma rays indirectly by recording the **Cherenkov light** emitted by charged particles created in **electromagnetic air showers**. Each event corresponds to the pattern of **pulses left by Cherenkov photons** on an array of photomultiplier tubes (PMTs) forming the telescope’s camera. Depending on the energy of the primary particle, from a few hundred to tens of thousands of photons are collected, producing characteristic **shower images** that enable **statistical discrimination** between gamma and hadron events.

> ⚠️ **Notes**
> • The number of hadron (`h`) events is **underrepresented**; in real data they dominate.
> • **Simple accuracy** is not an adequate metric — models should be compared using **ROC curves**.
> • Relevant ROC operating points correspond to background acceptance rates below **0.01, 0.02, 0.05, 0.1, or 0.2**, depending on the required sample purity.

This dataset provides an introductory example of **signal-vs-background classification** in observational high-energy astrophysics and can be used to explore feature selection, imbalance handling, and evaluation techniques common in experimental physics.

---

## 📚 Citation
> Bock R. K. et al. (2004). *MAGIC Gamma Telescope Data*. UCI Machine Learning Repository.
> [https://archive.ics.uci.edu/ml/datasets/MAGIC+Gamma+Telescope](https://archive.ics.uci.edu/ml/datasets/MAGIC+Gamma+Telescope)

> Sloan Digital Sky Survey (SDSS) Collaboration, *SDSS DR17: The Seventeenth Data Release of the Sloan Digital Sky Survey*, Astrophysical Journal Supplement Series, 2022.
> [https://www.sdss.org](https://www.sdss.org)

> **GalaxiesML Project**, *HSC GalaxiesML: Hyper Suprime-Cam Photometric and Spectroscopic Galaxy Data*, UCLA DataLab.
> [https://datalab.astro.ucla.edu/galaxiesml.html](https://datalab.astro.ucla.edu/galaxiesml.html)

> **HSC-SSP Collaboration**, *Hyper Suprime-Cam Subaru Strategic Program (HSC-SSP) Data Release*.

> Sloan Digital Sky Survey (SDSS) Collaboration, *SDSS DR17: The Seventeenth Data Release of the Sloan Digital Sky Survey*, Astrophysical Journal Supplement Series, 2022.
> [https://www.sdss.org](https://www.sdss.org)

