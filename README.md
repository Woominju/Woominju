<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f172a,55:1e3a8a,100:3b82f6&height=210&section=header&text=Minju%20Woo&fontSize=52&fontColor=ffffff&fontAlignY=36&desc=Data-centric%20ML%20%C2%B7%20Time-Series%20Anomaly%20Detection%20%C2%B7%20Evaluation&descSize=17&descAlignY=58&animation=fadeIn" alt="Minju Woo" width="100%" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/HUFS-Mathematics%20%C2%B7%20Finance%20%26%20AI-1e3a8a?style=flat-square" alt="HUFS" />
  <img src="https://img.shields.io/badge/Lab-Financial%20Engineering-3b82f6?style=flat-square" alt="Financial Engineering Lab" />
  <a href="https://github.com/Woominju/PWTA"><img src="https://img.shields.io/badge/Thesis-PWTA-0f172a?style=flat-square&logo=github&logoColor=white" alt="PWTA" /></a>
</p>

<br />

I'm a math undergraduate at Hankuk University of Foreign Studies, with a double major in Finance & AI.
Most of my research so far has been on anomaly detection in multivariate time series.
While working on it, I found that the data itself (how it is scaled, which channels carry the signal, how results are scored) changed the results much more than the model architecture did.
That is the part of ML I want to keep working on.

<br />

## 🔭 Research Interests

<table>
  <tr>
    <td width="50%" valign="top">
      <b>📊 Data-centric machine learning</b><br />
      <sub>How the properties of training and test data affect what a model learns, and how to select or reshape data to fix that</sub>
    </td>
    <td width="50%" valign="top">
      <b>🧪 Synthetic data</b><br />
      <sub>Synthetic data for training models</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <b>📏 Evaluation methods for ML</b><br />
      <sub>Especially metrics that can make a weak model look strong</sub>
    </td>
    <td width="50%" valign="top">
      <b>📈 Multivariate time series</b><br />
      <sub>Time-series modeling and anomaly detection</sub>
    </td>
  </tr>
</table>

<br />

## 🧬 Research Experience

### Undergraduate Researcher, Financial Engineering Lab, HUFS
<sub>Jun 2025 – Aug 2026 · advisor: Prof. Hyeongwoo Kong</sub>

#### ⭐ [PWTA: Patch-Window Transformer Autoencoder](https://github.com/Woominju/PWTA) <sub>undergraduate thesis</sub>

<table>
  <tr>
    <td align="center" width="25%"><h3>0.15M</h3><sub>parameters</sub></td>
    <td align="center" width="25%"><h3>32×</h3><sub>fewer than Anomaly Transformer</sub></td>
    <td align="center" width="25%"><h3>+0.055</h3><sub>macro PR-AUC over lab baseline</sub></td>
    <td align="center" width="25%"><h3>5 / 5</h3><sub>seeds, all 4 metrics</sub></td>
  </tr>
</table>

- Built a small patch-based Transformer autoencoder in PyTorch for multivariate time-series anomaly detection (about 0.15M parameters, 32x fewer than Anomaly Transformer).
- Tried 37+ architecture and hyperparameter settings. Accuracy barely changed, so I focused on the data and the scoring instead.
- On SMAP and MSL, 42% and 77% of the channels are almost constant. z-score normalization blew up tiny changes in these channels and hid the real signal, so I kept the original scale.
- Anomalies often show up as sudden jumps in channels that are normally constant, so I kept those channels instead of dropping them.
- Point-adjusted F1 gives random scores 0.83 (Kim et al., AAAI 2022), so I reported raw PR-AUC, PA%K, best F1 and VUS-PR. I only counted an improvement if it held on all 5 seeds.
- My final scoring method improved macro PR-AUC by 0.055 over the lab's kurtosis-weighted baseline on SMD, SMAP and MSL (all 5 seeds, all 4 metrics). It was slightly worse on SWaT (-0.004).

#### 📐 Adaptive Kurtosis-Weighted Channel Fusion <sub>co-first author, manuscript in preparation</sub>
- Looked at channel dilution: an anomaly usually affects only a few channels, so averaging errors over all channels weakens it.
- Analyzed kurtosis-weighted fusion of channel scores and when it fails (when anomalies are dense, e.g. 28% of PSM).
- Did the mathematical validation and ran the evaluation on 10 existing detectors.

#### 🏦 Synthetic data for loan-approval models <sub>industry collaboration with KCIS</sub>
- Took part in research on generating synthetic data to train loan-approval models.

#### 💼 Decision-focused learning for minimum-variance portfolios <sub>co-author, research report</sub>
- Wrote the mathematical formulation. Small errors in the estimated covariance get amplified by the matrix inverse and change the portfolio weights a lot, which is why the model is trained on the decision loss.

<br />

## 📝 Manuscript

> S. Park\*, **M. Woo\***, and H. Kong. *Adaptive Kurtosis-Weighted Channel Fusion for Multivariate Time-Series Anomaly Detection.* In preparation. <sub>(\*equal contribution)</sub>

<br />

## 🎓 Education

**Hankuk University of Foreign Studies** — B.S. in Mathematics, double major in Finance & AI
<sub>Mar 2023 – present · GPA 4.17 / 4.50</sub>

<sub><b>Relevant coursework:</b> Linear Algebra I-II · Introduction to Analysis I-II · Statistics I-II · Convex Optimization · Computational Mathematics · Differential Equations · Differential Geometry</sub>

<br />

## 🧑‍🏫 Teaching & Activities

- Teaching assistant for Mathematics for Artificial Intelligence, HUFS (Spring 2026)
- Presented research updates at the lab's biweekly seminars
- Attended ICAIF 2025 and the 2026 Korean Operations Research and Management Science Society Conference

<br />

## 🏆 Awards

| Year | Award |
|:---:|---|
| 2025 | HUFStudy Literature Review & Presentation Award, **Grand Prize** |
| 2025 | Youngji Foundation Scholarship |
| 2024 | Dean's Scholarship for Academic Excellence, two semesters |
| 2023 | English Speech Contest, 2nd prize, June and November |

<br />

## 🛠 Skills

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white" alt="PyTorch" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white" alt="NumPy" />
  <img src="https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white" alt="pandas" />
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white" alt="scikit-learn" />
  <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white" alt="TensorFlow" />
  <img src="https://img.shields.io/badge/CVXPY-475569?style=flat-square" alt="CVXPY" />
  <img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white" alt="Streamlit" />
  <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white" alt="Git" />
</p>

<br />

## 📂 Repositories

**Research**

| Repository | Description |
|---|---|
| [PWTA](https://github.com/Woominju/PWTA) | Code for my undergraduate thesis |
| [paper-implementations](https://github.com/Woominju/paper-implementations) | Small implementations of papers I read, linked to my Notion notes |

**Projects & Coursework**

| Repository | Description |
|---|---|
| [streamlit-dashboard](https://github.com/Woominju/streamlit-dashboard) | Streamlit and Plotly dashboard practice |
| [deep-learning-coursework](https://github.com/Woominju/deep-learning-coursework) | Deep learning class assignments (2023) |
| [heart-disease-ann](https://github.com/Woominju/heart-disease-ann) | ANN for heart disease prediction |
| [hotel-reservation-dataset](https://github.com/Woominju/hotel-reservation-dataset) | Hotel booking cancellation data |
| [smiling-face-cnn](https://github.com/Woominju/smiling-face-cnn) | CNN for smiling vs. non-smiling faces |
| [logic-and-programming](https://github.com/Woominju/logic-and-programming) | Python and pandas exercises |
| [git-conflict-practice](https://github.com/Woominju/git-conflict-practice) | Git branching and merge conflict practice |

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f172a,55:1e3a8a,100:3b82f6&height=110&section=footer" alt="" width="100%" />
</p>
