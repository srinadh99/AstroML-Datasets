# Astronomy, Astrophysics, and Space Physics ML Course Projects

## Classical-ML-only project ideas for course use

This version is restricted to **Astronomy, Astrophysics, and Space Physics** and uses **classical machine learning only** — no deep learning suggestions.

The projects are ordered roughly from **easier undergraduate projects** to **stronger upper-level / graduate-level projects**.

---

## 1. Galaxy Redshift Prediction (SDSS)

**Problem statement:** Predict the spectroscopic redshift of galaxies using only broad-band photometric measurements such as the SDSS `u`, `g`, `r`, `i`, and `z` magnitudes. This is a very natural introductory regression problem because the input is clean tabular data, the target has direct physical meaning, and students can compare simple linear baselines with stronger nonlinear models.

**Task:** Regression

**Setting:** Supervised learning

**Suggested methods / algorithms:** Linear Regression, Ridge/Lasso, k-Nearest Neighbors Regressor, Random Forest Regressor, Gradient Boosting / XGBoost

**Dataset source:** SDSS DR17 photometric and spectroscopic tables. The easiest route is to export a matched CSV from SDSS or Astro Data Lab containing photometric magnitudes and spectroscopic redshift. Official sources: [SDSS DR17 photo-z documentation](https://www.sdss4.org/dr17/algorithms/photo-z/), [NOIRLab Astro Data Lab SDSS access](https://datalab.noirlab.edu/data/sdss)

**Level:** Introductory undergraduate

**Recommended workflow:** 1. Build a clean galaxy-only table. 2. Compare raw magnitudes versus color indices such as `u-g`, `g-r`, `r-i`, `i-z`. 3. Train linear and tree-based regressors. 4. Evaluate with MAE, RMSE, and residuals as a function of redshift.

---

## 2. Galaxy Redshift Prediction (HSC • GalaxiesML)

**Problem statement:** Estimate galaxy redshift from Hyper Suprime-Cam multiband photometry. Compared with SDSS, this gives a slightly richer and deeper survey dataset, which makes it a good second-level project after a basic photo-z exercise.

**Task:** Regression

**Setting:** Supervised learning

**Suggested methods / algorithms:** Ridge Regression, kNN Regressor, Random Forest Regressor, Extra Trees, CatBoost, XGBoost

**Dataset source:** [GalaxiesML](https://datalab.astro.ucla.edu/galaxiesml.html), built from the Hyper Suprime-Cam Survey with spectroscopic redshifts as labels. Students can use the tabular photometry directly.

**Level:** Undergraduate to intermediate

**Recommended workflow:** 1. Use only tabular photometric columns at first. 2. Remove bad or missing measurements. 3. Benchmark tree ensembles against a linear baseline. 4. Study performance versus brightness and redshift.

---

## 3. Star–Galaxy–Quasar Classification (SDSS)

**Problem statement:** Classify astronomical sources into stars, galaxies, and quasars using SDSS photometric features. This is a classic multiclass astronomy problem and works very well for a first classification assignment because the classes are physically meaningful and the features are easy to visualize in color–color space.

**Task:** Multiclass classification

**Setting:** Supervised learning

**Suggested methods / algorithms:** Logistic Regression, Linear SVM, RBF SVM, Random Forest, Gradient Boosting, XGBoost

**Dataset source:** SDSS photometric tables matched to spectroscopic object class labels. The easiest route is to export a prepared CSV from SDSS or Astro Data Lab. Official sources: [SDSS DR17](https://www.sdss4.org/dr17/), [NOIRLab Astro Data Lab SDSS](https://datalab.noirlab.edu/data/sdss)

**Level:** Introductory undergraduate

**Recommended workflow:** 1. Build color features from magnitudes. 2. Train binary models first for star-vs-galaxy. 3. Extend to full three-class classification. 4. Evaluate using confusion matrix, macro-F1, and class-wise precision/recall.

---

## 4. Galaxy Morphology Classification (Galaxy Zoo + SDSS Features)

**Problem statement:** Predict broad galaxy morphology classes such as spiral versus elliptical using Galaxy Zoo labels together with SDSS photometric and structural features. This avoids raw-image deep learning and keeps the project within classical ML by using catalog features or hand-crafted image descriptors.

**Task:** Binary or multiclass classification

**Setting:** Supervised learning

**Suggested methods / algorithms:** Logistic Regression, Random Forest, Extra Trees, SVM, Gradient Boosting

**Dataset source:** [Galaxy Zoo data portal](https://data.galaxyzoo.org/) with volunteer morphology labels, combined with SDSS tabular features such as colors, concentration, size, axis ratio, and surface brightness.

**Level:** Undergraduate to intermediate

**Recommended workflow:** 1. Convert Galaxy Zoo vote fractions into clean labels. 2. Join those labels to SDSS features. 3. Compare linear and nonlinear classifiers. 4. Analyze which physical features matter most.

---

## 5. Galaxy Merger Detection (Galaxy Zoo Mergers)

**Problem statement:** Identify likely merging or interacting galaxies using merger labels and simple tabular or hand-crafted image features. This is a good project for students who want a physically interesting classification problem without using deep neural networks.

**Task:** Binary classification

**Setting:** Supervised learning

**Suggested methods / algorithms:** Logistic Regression, Random Forest, SVM, Gradient Boosting, Isolation Forest as an outlier baseline

**Dataset source:** [Galaxy Zoo: Mergers](https://data.galaxyzoo.org/mergers.html). Students can use provided merger labels and combine them with SDSS metadata or with simple image descriptors such as asymmetry, concentration, or Gini/M20 if available.

**Level:** Intermediate undergraduate

**Recommended workflow:** 1. Build a balanced labeled sample. 2. Start with tabular structural features. 3. Try hand-crafted morphology descriptors if images are used. 4. Compare accuracy, ROC-AUC, and precision at high recall.

---

## 6. Gamma / Hadron Event Classification (MAGIC Telescope)

**Problem statement:** Distinguish gamma-ray events from hadronic background events recorded by an atmospheric Cherenkov telescope. This is a standard signal-vs-background problem in astroparticle physics and is one of the cleanest physics-flavored binary classification benchmarks.

**Task:** Binary classification

**Setting:** Supervised learning

**Suggested methods / algorithms:** Logistic Regression, Decision Trees, Random Forest, AdaBoost, Gradient Boosting, XGBoost

**Dataset source:** [UCI MAGIC Gamma Telescope dataset](https://archive.ics.uci.edu/ml/datasets/magic%2Bgamma%2Btelescope)

**Level:** Introductory undergraduate

**Recommended workflow:** 1. Inspect class balance and feature distributions. 2. Train a simple logistic baseline. 3. Compare ensemble models. 4. Evaluate using ROC-AUC and operating points relevant to rare-signal detection.

---

## 7. Pulsar Candidate Classification (HTRU2)

**Problem statement:** Identify real pulsar candidates from summary statistics produced by a radio pulsar survey pipeline. This is an excellent first ML project because the features are already prepared, the labels are binary, and the scientific interpretation is straightforward.

**Task:** Binary classification

**Setting:** Supervised learning

**Suggested methods / algorithms:** Logistic Regression, kNN, SVM, Random Forest, XGBoost

**Dataset source:** [UCI HTRU2 dataset](https://archive.ics.uci.edu/ml/datasets/HTRU2)

**Level:** Introductory undergraduate

**Recommended workflow:** 1. Examine imbalance and outliers. 2. Build a logistic-regression baseline. 3. Compare SVM and tree ensembles. 4. Use precision, recall, F1, and ROC-AUC rather than accuracy alone.

---

## 8. Exoplanet Candidate Disposition Classification (Kepler KOI)

**Problem statement:** Predict whether a Kepler Object of Interest is a confirmed planet candidate, a false positive, or another catalog disposition using tabular transit and stellar parameters. This project is very attractive for students because the labels come from a real mission pipeline and the feature set is accessible as a table.

**Task:** Binary or multiclass classification

**Setting:** Supervised learning

**Suggested methods / algorithms:** Logistic Regression, Random Forest, Gradient Boosting, XGBoost, calibrated SVM

**Dataset source:** NASA Exoplanet Archive KOI cumulative table. Official sources: [NASA Exoplanet Archive](https://exoplanetarchive.ipac.caltech.edu/), [Kepler KOI documentation](https://exoplanetarchive.ipac.caltech.edu/docs/Kepler_KOI_docs.html)

**Level:** Undergraduate to intermediate

**Recommended workflow:** 1. Select a clean target label definition. 2. Remove leakage columns that directly encode final disposition. 3. Train several tabular classifiers. 4. Evaluate with confusion matrix and class-wise metrics.

---

## 9. Transit Light-Curve Anomaly Detection (Kepler or TESS)

**Problem statement:** Detect unusual transit-like or nonstandard light curves that may correspond to rare astrophysical systems, instrumental artifacts, or pipeline failures. This project introduces unsupervised learning using physically interpretable time-series features.

**Task:** Anomaly detection

**Setting:** Unsupervised or semi-supervised learning

**Suggested methods / algorithms:** PCA, Isolation Forest, One-Class SVM, Local Outlier Factor, Gaussian Mixture Models on extracted features

**Dataset source:** Public Kepler or TESS light curves from MAST. Official sources: [Kepler at MAST](https://archive.stsci.edu/missions-and-data/kepler), [Kepler public light curves](https://archive.stsci.edu/kepler/publiclightcurves.html), [TESS at MAST](https://archive.stsci.edu/missions-and-data/tess)

**Level:** Intermediate undergraduate

**Recommended workflow:** 1. Extract summary features such as period, depth, duration, skewness, and variability indices. 2. Fit unsupervised models on normal-looking light curves. 3. Rank anomalies. 4. Inspect the highest-scoring candidates manually.

---

## 10. Variable-Star Classification (Gaia DR3)

**Problem statement:** Classify variable stars into astrophysical types using Gaia variability tables and source parameters. This is a rich multiclass project that introduces students to class imbalance, noisy labels, and feature selection in a real survey dataset.

**Task:** Multiclass classification

**Setting:** Supervised learning

**Suggested methods / algorithms:** Logistic Regression, Random Forest, Extra Trees, XGBoost, CatBoost

**Dataset source:** Gaia DR3 variability products and source parameters. Official sources: [Gaia DR3 overview](https://www.cosmos.esa.int/web/gaia/dr3), [Gaia DR3 papers](https://www.cosmos.esa.int/web/gaia/dr3-papers)

**Level:** Intermediate undergraduate

**Recommended workflow:** 1. Select a manageable subset of variable classes. 2. Join variability labels with photometric and astrometric features. 3. Compare class weighting and resampling strategies. 4. Evaluate with macro-F1 and per-class recall.

---

## 11. HR-Diagram Clustering and Stellar Outlier Detection (Gaia DR3)

**Problem statement:** Use Gaia parallax and photometry to build a Hertzsprung–Russell diagram, then cluster stellar populations and identify unusual sources. This is a clean unsupervised project that connects machine learning directly to a central concept in stellar astrophysics.

**Task:** Clustering and anomaly detection

**Setting:** Unsupervised learning

**Suggested methods / algorithms:** PCA, k-means, Gaussian Mixture Models, DBSCAN, HDBSCAN, Isolation Forest

**Dataset source:** Gaia DR3 source catalog with parallax and photometry. Official source: [Gaia DR3](https://www.cosmos.esa.int/web/gaia/dr3)

**Level:** Introductory to intermediate undergraduate

**Recommended workflow:** 1. Compute absolute magnitude from parallax. 2. Build color–magnitude features. 3. Cluster the HR diagram. 4. Investigate outliers such as white dwarfs, binaries, or poor-quality measurements.

---

## 12. Photometric Transient Classification (PLAsTiCC)

**Problem statement:** Classify simulated LSST-like transient and variable objects from multiband light curves. This is a strong course project for students who want a more realistic time-domain astronomy dataset while still staying fully within feature-based classical ML.

**Task:** Multiclass classification

**Setting:** Supervised learning

**Suggested methods / algorithms:** Feature extraction + Random Forest, Gradient Boosting, XGBoost, LightGBM, calibrated SVM

**Dataset source:** [PLAsTiCC unblinded data on Zenodo](https://zenodo.org/records/2539456), with project information at [PLAsTiCC](https://plasticc.org/)

**Level:** Intermediate to advanced undergraduate

**Recommended workflow:** 1. Engineer light-curve features for each band. 2. Handle missing and irregular sampling carefully. 3. Train class-weighted multiclass models. 4. Evaluate with balanced metrics and confusion patterns between transient types.

---

## 13. Novelty Detection in ZTF Light Curves

**Problem statement:** Search ZTF light curves for unusual or previously unseen variability patterns. This is a good unsupervised project for students interested in discovery-oriented astronomy rather than standard closed-set classification.

**Task:** Anomaly detection / novelty detection

**Setting:** Unsupervised learning

**Suggested methods / algorithms:** PCA, Isolation Forest, One-Class SVM, Local Outlier Factor, Gaussian Mixture Models

**Dataset source:** ZTF public objects and light-curve tables. Official sources: [IRSA ZTF mission page](https://irsa.ipac.caltech.edu/Missions/ztf.html), [ZTF light-curve API](https://irsa.ipac.caltech.edu/docs/program_interface/ztf_lightcurve_api.html)

**Level:** Advanced undergraduate

**Recommended workflow:** 1. Download a manageable subset of light curves. 2. Extract variability features such as amplitude, period, color, skewness, and structure-function summaries. 3. Fit anomaly-detection models. 4. Inspect top candidates and separate real rare objects from bad data.

---

## 14. Gamma-Ray Source Classification (Fermi LAT 4FGL-DR4)

**Problem statement:** Classify gamma-ray sources, for example pulsars versus blazars, using catalog-level spectral and variability features from the Fermi LAT source catalog. This is an excellent upper-level project because it combines astrophysical interpretation with high-quality tabular data.

**Task:** Binary or multiclass classification

**Setting:** Supervised learning

**Suggested methods / algorithms:** Logistic Regression, Random Forest, XGBoost, SVM, probabilistic calibration

**Dataset source:** Official Fermi LAT source catalog pages: [Fermi LAT 14-year catalog (4FGL-DR4)](https://fermi.gsfc.nasa.gov/ssc/data/access/lat/14yr_catalog/), [4FGL original catalog page](https://fermi.gsfc.nasa.gov/ssc/data/access/lat/8yr_catalog/)

**Level:** Advanced undergraduate to graduate

**Recommended workflow:** 1. Select a well-labeled subset such as pulsars and blazars. 2. Use only catalog features available for all sources. 3. Compare interpretable linear models with boosted trees. 4. Examine feature importance and probabilistic confidence.

---

## 15. Sunspot Number Forecasting

**Problem statement:** Forecast future sunspot counts from historical observations. This is one of the simplest space-physics forecasting projects and works well for introducing lag features, trend/cycle structure, and model comparison on a univariate time series.

**Task:** Time-series regression / forecasting

**Setting:** Supervised learning

**Suggested methods / algorithms:** Linear Regression on lag features, Ridge Regression, Random Forest Regressor, Gradient Boosting, Support Vector Regression, ARIMA as a baseline

**Dataset source:** [SILSO Sunspot Number data files](https://www.sidc.be/SILSO/datafiles)

**Level:** Introductory undergraduate

**Recommended workflow:** 1. Start with monthly sunspot numbers. 2. Build lagged features and rolling statistics. 3. Compare ML regressors against a naive persistence model and ARIMA. 4. Evaluate with RMSE and backtesting by forecast horizon.

---

## 16. Solar Flare Class Prediction (GOES X-ray Flux + Event Reports)

**Problem statement:** Predict whether the Sun will produce a significant flare, such as a C-, M-, or X-class event, from recent X-ray flux history and related space-weather indicators. This project is attractive because the target has operational value and the data are openly available.

**Task:** Classification

**Setting:** Supervised learning

**Suggested methods / algorithms:** Logistic Regression, Random Forest, Gradient Boosting, XGBoost, Support Vector Machine

**Dataset source:** NOAA SWPC products and reports. Official sources: [GOES X-ray Flux](https://www.swpc.noaa.gov/products/goes-x-ray-flux), [Solar and Geophysical Event Reports](https://www.swpc.noaa.gov/products/solar-and-geophysical-event-reports)

**Level:** Intermediate undergraduate

**Recommended workflow:** 1. Define a forecasting target such as whether an M-class flare occurs in the next 24 hours. 2. Create lagged and rolling features from GOES flux. 3. Train class-balanced classifiers. 4. Evaluate with precision-recall curves and event-based recall.

---

## 17. Geomagnetic Activity / Kp Forecasting (OMNI + Kp)

**Problem statement:** Forecast geomagnetic activity, such as the planetary Kp index, from upstream solar-wind and interplanetary magnetic-field measurements. This is a strong space-physics ML project because the physical driver–response relationship is clear and the data are readily available.

**Task:** Regression or classification

**Setting:** Supervised learning

**Suggested methods / algorithms:** Ridge Regression, Random Forest, Gradient Boosting, XGBoost, Support Vector Regression, Gaussian Process Regression on smaller subsets

**Dataset source:** NASA OMNI data products and associated geomagnetic indices. Official sources: [OMNIWeb](https://omniweb.gsfc.nasa.gov/), [OMNI Data Explorer](https://omniweb.gsfc.nasa.gov/form/dx1.html)

**Level:** Intermediate to advanced undergraduate

**Recommended workflow:** 1. Download 1-hour or 5-minute OMNI data. 2. Build lagged solar-wind and IMF features. 3. Predict future Kp or classify storm vs non-storm intervals. 4. Evaluate by lead time and storm-event performance.

---

## 18. Stellar Parameter Prediction from APOGEE Spectra Metadata

**Problem statement:** Predict stellar parameters such as effective temperature, surface gravity, or metallicity using catalog-level APOGEE measurements and selected summary features. To keep the problem within a classical-ML course, students should use tabular parameters or engineered spectral summaries rather than raw spectra.

**Task:** Regression

**Setting:** Supervised learning

**Suggested methods / algorithms:** Linear Regression, Ridge/Lasso, Random Forest Regressor, Gradient Boosting, Gaussian Process Regression on a smaller subset

**Dataset source:** SDSS APOGEE summary catalogs and stellar-parameter products. Official sources: [APOGEE DR17](https://www.sdss4.org/dr17/irspec/), [Using APOGEE stellar parameters](https://www.sdss4.org/dr17/irspec/parameters/)

**Level:** Advanced undergraduate

**Recommended workflow:** 1. Select one target parameter such as `Teff` or `[Fe/H]`. 2. Use high-quality tabular predictors only. 3. Benchmark linear versus nonlinear regressors. 4. Study which observables best constrain each parameter.

---

## 19. Asteroid Taxonomy Classification from SDSS Colors

**Problem statement:** Classify asteroids into taxonomic groups using SDSS photometric colors and orbital descriptors. This is a nice astronomy project because the input data are low-dimensional, physically interpretable, and closely tied to surface composition.

**Task:** Multiclass classification

**Setting:** Supervised learning

**Suggested methods / algorithms:** Logistic Regression, Linear Discriminant Analysis, Random Forest, SVM, Gradient Boosting

**Dataset source:** SDSS Moving Object Catalog and related taxonomy tables. Official sources: [SDSS Moving Object Catalog resource](https://sbn.psi.edu/pds/resource/sdssmoc.html), [SDSS-based asteroid taxonomy dataset](https://data.nasa.gov/dataset/sdss-based-asteroid-taxonomy-v1-0-a1fcb)

**Level:** Undergraduate to intermediate

**Recommended workflow:** 1. Build color indices from asteroid photometry. 2. Join taxonomic labels where available. 3. Compare linear and nonlinear classifiers. 4. Analyze confusion between similar compositional classes.

---

## 20. TESS Object of Interest (TOI) Candidate Screening

**Problem statement:** Use tabular TESS candidate and stellar features to predict whether a TESS Object of Interest is likely to be promoted, demoted, or remain a promising candidate. This is similar in spirit to the Kepler KOI project but uses the TESS ecosystem.

**Task:** Binary or multiclass classification

**Setting:** Supervised learning

**Suggested methods / algorithms:** Logistic Regression, Random Forest, Gradient Boosting, XGBoost, calibrated SVM

**Dataset source:** NASA Exoplanet Archive TOI tables and TESS documentation. Official sources: [TOI column definitions](https://exoplanetarchive.ipac.caltech.edu/docs/API_TOI_columns.html), [TESS TOI releases](https://tess.mit.edu/toi-releases/), [TESS Input Catalog](https://tess.mit.edu/science/tess-input-catalogue/)

**Level:** Intermediate undergraduate

**Recommended workflow:** 1. Define a clean label from TOI disposition or status fields. 2. Remove fields that trivially encode the target. 3. Train tabular classifiers. 4. Evaluate class-wise errors and compare with the Kepler version of the problem.

---

## Suggested progression for a course

**Best first projects for an introductory ML course:** 1, 3, 6, 7, 15

**Good mid-level semester projects:** 2, 4, 8, 10, 11, 16, 19, 20

**Stronger upper-level or graduate projects:** 5, 9, 12, 13, 14, 17, 18

---

## Notes

- Prefer **tabular subsets** first, even when the parent archive also contains images or spectra.
- For large archives, let students work on **a sampled CSV subset** instead of the full release.
- For classification tasks with class imbalance, encourage use of **precision, recall, F1, ROC-AUC, or PR-AUC**, not only accuracy.
- For regression tasks, require **MAE, RMSE, and residual plots**.
- For unsupervised projects, require both **quantitative scores** and **manual inspection of discovered clusters or anomalies**.

