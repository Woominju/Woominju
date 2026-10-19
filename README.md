# Minju Woo

I'm a math undergraduate at Hankuk University of Foreign Studies, with a double major in Finance & AI.
Most of my research so far has been on anomaly detection in multivariate time series.
While working on it, I found that the data itself (how it is scaled, which channels carry the signal, how results are scored) changed the results much more than the model architecture did.
That is the part of ML I want to keep working on.

## Research Interests

- Data-centric machine learning: how the properties of training and test data affect what a model learns, and how to select or reshape data to fix that
- Synthetic data for training models
- Evaluation methods for ML, especially metrics that can make a weak model look strong
- Multivariate time-series modeling and anomaly detection

## Research Experience

### Undergraduate Researcher, Financial Engineering Lab, HUFS
Jun 2025 - Aug 2026, advisor: Prof. Hyeongwoo Kong

**[PWTA: Patch-Window Transformer Autoencoder](https://github.com/Woominju/PWTA)** (undergraduate thesis)
- Built a small patch-based Transformer autoencoder in PyTorch for multivariate time-series anomaly detection (about 0.15M parameters, 32x fewer than Anomaly Transformer).
- Tried 37+ architecture and hyperparameter settings. Accuracy barely changed, so I focused on the data and the scoring instead.
- On SMAP and MSL, 42% and 77% of the channels are almost constant. z-score normalization blew up tiny changes in these channels and hid the real signal, so I kept the original scale.
- Anomalies often show up as sudden jumps in channels that are normally constant, so I kept those channels instead of dropping them.
- Point-adjusted F1 gives random scores 0.83 (Kim et al., AAAI 2022), so I reported raw PR-AUC, PA%K, best F1 and VUS-PR. I only counted an improvement if it held on all 5 seeds.
- My final scoring method improved macro PR-AUC by 0.055 over the lab's kurtosis-weighted baseline on SMD, SMAP and MSL (all 5 seeds, all 4 metrics). It was slightly worse on SWaT (-0.004).

**Adaptive Kurtosis-Weighted Channel Fusion** (co-first author, manuscript in preparation)
- Looked at channel dilution: an anomaly usually affects only a few channels, so averaging errors over all channels weakens it.
- Analyzed kurtosis-weighted fusion of channel scores and when it fails (when anomalies are dense, e.g. 28% of PSM).
- Did the mathematical validation and ran the evaluation on 10 existing detectors.

**Synthetic data for loan-approval models** (industry collaboration with KCIS)
- Took part in research on generating synthetic data to train loan-approval models.

**Decision-focused learning for minimum-variance portfolios** (co-author, research report)
- Wrote the mathematical formulation. Small errors in the estimated covariance get amplified by the matrix inverse and change the portfolio weights a lot, which is why the model is trained on the decision loss.

## Manuscript

S. Park\*, M. Woo\*, and H. Kong. Adaptive Kurtosis-Weighted Channel Fusion for Multivariate Time-Series Anomaly Detection. In preparation. (\*equal contribution)

## Education

Hankuk University of Foreign Studies, B.S. in Mathematics, double major in Finance & AI (Mar 2023 - present), GPA 4.17/4.50

Relevant coursework: Linear Algebra I-II, Introduction to Analysis I-II, Statistics I-II, Convex Optimization, Computational Mathematics, Differential Equations, Differential Geometry

## Teaching

Teaching assistant for Mathematics for Artificial Intelligence, HUFS (Spring 2026)

## Other Activities

- Presented research updates at the lab's biweekly seminars
- Attended ICAIF 2025 and the 2026 Korean Operations Research and Management Science Society Conference

## Awards

- HUFStudy Literature Review & Presentation Award, Grand Prize (2025)
- Youngji Foundation Scholarship (2025)
- Dean's Scholarship for Academic Excellence, two semesters (2024)
- English Speech Contest, 2nd prize, June and November (2023)

## Skills

Python, PyTorch, NumPy, pandas, scikit-learn, TensorFlow, CVXPY, Streamlit, Git

## Repositories

| Repository | Description |
|---|---|
| [PWTA](https://github.com/Woominju/PWTA) | Code for my undergraduate thesis |
| [paper-implementations](https://github.com/Woominju/paper-implementations) | Small implementations of papers I read, linked to my Notion notes |
| [streamlit-dashboard](https://github.com/Woominju/streamlit-dashboard) | Streamlit and Plotly dashboard practice |
| [deep-learning-coursework](https://github.com/Woominju/deep-learning-coursework) | Deep learning class assignments (2023) |
| [heart-disease-ann](https://github.com/Woominju/heart-disease-ann) | ANN for heart disease prediction |
| [hotel-reservation-dataset](https://github.com/Woominju/hotel-reservation-dataset) | Hotel booking cancellation data |
| [smiling-face-cnn](https://github.com/Woominju/smiling-face-cnn) | CNN for smiling vs. non-smiling faces |
| [logic-and-programming](https://github.com/Woominju/logic-and-programming) | Python and pandas exercises |
| [git-conflict-practice](https://github.com/Woominju/git-conflict-practice) | Git branching and merge conflict practice |
