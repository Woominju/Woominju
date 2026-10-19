# Minju Woo (우민주)

Mathematics undergraduate (double major in Finance & AI) at Hankuk University of Foreign Studies.
I study **how the data a model sees — its scale, sparsity, structure, and how we evaluate on it — decides what the model can learn**,
starting from multivariate time series and moving toward synthetic data and learning from data more broadly.

---

## Research Interests

- **Data-centric machine learning** — how properties of the training and test data (scaling, sparse or constant channels, how labels are defined) shape model behavior, and how to select or reshape data so a model learns the right signal.
- **Synthetic data** — generating data that is realistic enough to train on, and checking that models trained on it still behave well on real data.
- **Rigorous evaluation** — metrics and protocols that cannot be gamed: no point-adjustment illusions, results that hold on every seed, and honest reporting of where a method loses.
- **Multivariate time-series modeling and anomaly detection** — lightweight models whose gains come from better use of the data rather than larger architectures.

## Research Experience

### Undergraduate Researcher — Financial Engineering Lab, HUFS
*Jun 2025 – Aug 2026 · Advisor: Prof. Hyeongwoo Kong*

**PWTA: Patch-Window Transformer Autoencoder for time-series anomaly detection** — *Undergraduate thesis*
- Built a ~0.15M-parameter patch-based Transformer autoencoder in PyTorch: 32× fewer parameters and 45× less peak memory than Anomaly Transformer.
- Swept 37+ architecture and hyperparameter settings and found accuracy was flat across them; **the data-side choices moved performance instead.**
- **Input scaling:** on SMAP and MSL, 42% and 77% of channels are near-constant command flags. Re-normalizing them amplified tiny deviations by ~10⁸ and buried the real signal, so the pipeline keeps each dataset's native scale.
- **Rare-event channels:** anomalies often appear as sudden jumps in normally constant channels, so these channels are kept and triaged by how often they fire rather than dropped.
- **Evaluation:** reproduced the point-adjustment illusion (random scores reach 0.83 PA-F1; Kim et al., AAAI 2022) and reported raw PR-AUC, PA%K, best-F1 and VUS-PR instead. Every gain was required to be positive on all 5 seeds before it counted.
- Final unsupervised scoring stack: **+0.055 macro PR-AUC** over the lab's kurtosis-weighted baseline on SMD · SMAP · MSL, positive on all 5 seeds and all 4 metrics. The one dataset where it lost (SWaT, −0.004) is reported as is.

**Adaptive Kurtosis-Weighted Channel Fusion** — *Co-first author (manuscript in preparation)*
- Studied *channel dilution*: anomalies live in a few channels, but averaging channel-wise errors washes them out.
- Analyzed kurtosis-weighted fusion of channel scores and its failure condition (dense anomalies, e.g. PSM at 28%).
- Contributed mathematical validation and evaluation across 10 existing anomaly detectors.

**Synthetic Data for Loan-Approval Modeling** — *Industry–academia collaboration with KCIS*
- Participated in research on generating synthetic data for training loan-approval models.

**Decision-Focused Learning for Global Minimum-Variance Portfolios** — *Co-author, research report*
- Wrote the mathematical formulation. Showed how small covariance-estimation errors are amplified through the matrix inverse into large swings in portfolio weights, which motivates training the predictor on the decision loss instead of the estimation loss.

## Manuscript

- S. Park†, **M. Woo†**, and H. Kong. *Adaptive Kurtosis-Weighted Channel Fusion for Multivariate Time-Series Anomaly Detection.* In preparation. († equal contribution)

## Education

**Hankuk University of Foreign Studies (HUFS)** — B.S. in Mathematics, double major in Finance & AI · Mar 2023 – present · GPA 4.17 / 4.50
Relevant coursework: Linear Algebra I–II, Introduction to Analysis I–II, Statistics I–II, Convex Optimization, Computational Mathematics, Differential Equations, Differential Geometry

## Teaching

- Teaching Assistant, *Mathematics for Artificial Intelligence*, HUFS — Spring 2026

## Academic Activities

- Presented research updates at biweekly Financial Engineering Lab seminars.
- Attended ICAIF 2025 and the 2026 Korean Operations Research and Management Science Society Conference.

## Awards & Honors

- HUFStudy Literature Review & Presentation Award, Grand Prize — 2025
- Youngji Foundation Scholarship — 2025
- Dean's Scholarship for Academic Excellence (two semesters) — 2024
- English Speech Contest, Second Prize (June and November) — 2023

## Skills

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)
![CVXPY](https://img.shields.io/badge/CVXPY-2F4F4F?style=flat-square)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

Languages: Korean (native), English

## Repositories

| Repository | What it is |
|---|---|
| [streamlit-dashboard](https://github.com/Woominju/streamlit-dashboard) | Interactive data dashboards with Streamlit and Plotly |
| [Deep-learning](https://github.com/Woominju/Deep-learning) | Deep-learning coursework (2023): ANN, CNN, GAN, transfer learning, Hugging Face |
| [11-19-deep-learning-heart](https://github.com/Woominju/11-19-deep-learning-heart) | ANN classifier for heart-disease prediction |
| [11.26hotel-reservation](https://github.com/Woominju/11.26hotel-reservation) | Hotel booking cancellation dataset (k-fold model in Deep-learning) |
| [conflict-war](https://github.com/Woominju/conflict-war) | Git collaboration practice: branches, merge conflicts, reverts |
