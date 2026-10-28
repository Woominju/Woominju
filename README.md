<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f172a,55:1e3a8a,100:3b82f6&height=210&section=header&text=Minju%20Woo&fontSize=52&fontColor=ffffff&fontAlignY=36&desc=Mathematics%20%C2%B7%20Portfolio%20Optimization%20%C2%B7%20Financial%20Time%20Series&descSize=17&descAlignY=58&animation=fadeIn" alt="Minju Woo" width="100%" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/HUFS-Mathematics%20%C2%B7%20Finance%20%26%20AI-1e3a8a?style=flat-square" alt="HUFS" />
  <img src="https://img.shields.io/badge/Lab-Financial%20Engineering-3b82f6?style=flat-square" alt="Financial Engineering Lab" />
  <img src="https://img.shields.io/badge/GPA-4.17%20%2F%204.50-0f172a?style=flat-square" alt="GPA 4.17 / 4.50" />
</p>

<br />

I'm a mathematics undergraduate at Hankuk University of Foreign Studies, with a double major in Finance & AI, and an undergraduate researcher in the Financial Engineering Lab.
My work so far sits between financial mathematics and data: portfolio optimization, factor models for equity returns, credit-risk modeling, and financial time series.

The question I keep coming back to is how estimation error turns into bad decisions.
In a minimum-variance portfolio, a small error in the estimated covariance matrix is amplified by its inverse and changes the weights a lot; in my thesis, the evaluation metric alone decided which model looked best.
In graduate school I want to study these problems properly, with probability, stochastic analysis and statistics.

<br />

## 🔭 Research Interests

I am interested in **portfolio decisions built on estimated risk**: how errors in estimated risk propagate into portfolio weights, and how stochastic models of asset prices and volatility can make portfolio construction more reliable.

<table>
  <tr>
    <td width="50%" valign="top">
      <b>💼 Portfolio construction under estimation error</b><br />
      <sub>How errors in estimated means and covariances propagate to portfolio weights, and how to build portfolios that hold up against them</sub>
    </td>
    <td width="50%" valign="top">
      <b>📈 Stochastic models of asset prices and volatility</b><br />
      <sub>Continuous-time and time-series models of returns and volatility, which I want to study more rigorously in graduate school</sub>
    </td>
  </tr>
</table>

<br />

## 🧬 Research Experience

### Undergraduate Researcher, Financial Engineering Lab, HUFS
<sub>Jun 2025 – present · advisor: Prof. Hyeongwoo Kong</sub>

#### 💼 Decision-focused learning for minimum-variance portfolios <sub>co-author, research report</sub>

The minimum-variance portfolio depends on the covariance estimate only through its inverse:

```math
w^\star(\Sigma) = \arg\min_{\mathbf{1}^\top w = 1} \; w^\top \Sigma\, w = \frac{\Sigma^{-1}\mathbf{1}}{\mathbf{1}^\top \Sigma^{-1}\mathbf{1}}
```

- Reviewed and contributed to the mathematical formulation of the project.
- When $`\Sigma`$ is ill-conditioned, a small error in $`\hat\Sigma`$ is amplified by $`\hat\Sigma^{-1}`$ and changes the weights a lot, so a covariance model that is accurate in the usual statistical sense can still give a poor portfolio. This is why the model is trained on the decision loss, the realized risk of $`w^\star(\hat\Sigma)`$, rather than on covariance estimation error alone.

#### ⭐ [PWTA: Patch-wise Transformer Autoencoder](https://github.com/Woominju/PWTA) <sub>undergraduate thesis · [PDF](https://github.com/Woominju/PWTA/blob/main/thesis/PWTA_thesis.pdf)</sub>

<table>
  <tr>
    <td align="center" width="25%"><h3>0.15M</h3><sub>parameters</sub></td>
    <td align="center" width="25%"><h3>51 / 110</h3><sub>entities ranked first under raw PR-AUC</sub></td>
    <td align="center" width="25%"><h3>10.8×</h3><sub>Anomaly Transformer's raw PR-AUC on SMD</sub></td>
    <td align="center" width="25%"><h3>1.00×</h3><sub>random: Anomaly Transformer at 0.935 point-adjusted F1</sub></td>
  </tr>
</table>

- Re-evaluated multivariate time-series anomaly detectors with raw point-level PR-AUC instead of point-adjusted F1. Anomaly Transformer reproduced its published point-adjusted F1 (0.935 on MSL, 0.965 on SMAP) but scored at the random baseline; on SWaT, DCdetector output exactly zero for 97.9% of time points.
- Under the same metric, PWTA, a small patch-based Transformer autoencoder, ranked first on 51 of 110 entities (mean PR-AUC 0.431 vs. 0.317 for the best classical baseline). It has a clear limit: on SWaT, where attacks stay inside the normal value range, Isolation Forest was better.
- On SMAP and MSL, 42% and 77% of the channels are almost constant; z-score normalization divides them by a standard deviation near zero and hides the real signal, so the original scale was kept. Improvements were only counted if they held on all 5 seeds.

#### 📐 Adaptive Kurtosis-Weighted Channel Fusion <sub>co-first author, manuscript in preparation</sub>
- Co-developed a training-free weighting rule that weights channel-wise anomaly scores by their excess kurtosis. An anomaly usually affects only a few channels, so averaging errors over all channels weakens it; kurtosis weighting favours channels that are usually quiet and then spike.
- Led the theoretical analysis of when kurtosis weighting improves separation over uniform weighting under a sparse-channel model, including when it fails (dense anomalies, e.g. 28% of PSM), and ran the evaluation on 10 existing detectors.

#### 🏦 Synthetic data for loan-approval models <sub>industry project with KCIS · Mar – Jun 2026</sub>
- Analyzed real-world credit data and compared model performance on real vs. synthetic data.

<br />

## 📈 Quantitative Finance Projects

#### [Deep Multi-Factor Model on KOSPI](https://github.com/Woominju/dmfm-kospi) <sub>team project with Sahong Park · Investment Theory and Optimization</sub>
- Replicated the Deep Multi-Factor Model (Wei, Dai & Lin, 2022) on 934 KOSPI stocks over 2013–2025: graph attention networks estimate industry and market effects, which are subtracted from each stock's latent context before the factor is formed.
- Long–short top/bottom-10 portfolio, net of commission, slippage and borrowing costs: **net Sharpe 2.73** vs. 2.18 for the same graphs without neutralization and 1.36 for a linear factor model, positive in all three test sub-periods. The test window overlaps Korea's 2023–2025 short-selling ban, which the README notes.

#### [Does SMOTE change what a credit model thinks matters?](https://github.com/Woominju/smote-feature-importance-stability) <sub>team project with Suyeon Oh · Business Analytics</sub>
- Walk-forward study on 1.76M Lending Club loans (train ≤ year *t*, test year *t*+1). SMOTE lowered AUROC and average precision in all 36 comparisons; F1 rose only because of the fixed 0.5 threshold. It also reshuffled feature-importance ranks, and the README discusses why interpolating label-encoded categoricals is a likely cause.

#### [Robust portfolio optimization (worst-case)](https://github.com/Woominju/paper-implementations/tree/main/finance/robust_portfolio)
- Implemented the worst-case approach to mean-variance optimization with an ellipsoidal uncertainty set for expected returns, solved as a second-order cone program in CVXPY, and compared it with the plain mean-variance portfolio.

#### [Credit-risk preprocessing case study](https://github.com/Woominju/credit-risk-analysis)
- An IQR clipping rule applied to every numeric column set Q1 = Q3 for the binary credit-history flag, rewrote every bad-credit applicant as "meets guidelines", and erased the strongest feature. The original pipeline scored at or below the majority-class baseline (0.65); clipping only the continuous columns raised test accuracy to 0.79.

<br />

## 📝 Manuscript

> S. Park\*, **M. Woo\***, and H. Kong. *Adaptive Kurtosis-Weighted Channel Fusion for Multivariate Time-Series Anomaly Detection.* In preparation. <sub>(\*equal contribution)</sub>

<br />

## 🎓 Education

**Hankuk University of Foreign Studies**, B.S. in Mathematics, double major in Finance & AI
<sub>Mar 2023 – Feb 2027 (expected) · GPA 4.17 / 4.50</sub>

| | Coursework |
|---|---|
| **Mathematics** | Introduction to Analysis I-II · Metric Spaces · Topology · Linear Algebra I-II · Modern Algebra I-II · Differential Equations · Differential Geometry · Computational Mathematics · Probability Theory (in progress) |
| **Finance** | Financial Mathematics · Financial Time Series Analysis · Investment Theory and Optimization · Financial Markets |
| **Statistics & optimization** | Statistics I-II · Convex Optimization · Introduction to Operations Research · Statistical Learning with Python |
| **Data & ML** | Data Mining · Big Data Analysis · Big Data Modeling · Data Structures · Advanced Business Analytics · Finance & AI Capstone |

<br />

## 🧑‍🏫 Teaching & Activities

- Teaching assistant, Mathematics for Artificial Intelligence, HUFS (Spring 2026)
- Teaching mentor, Calculus, HUFS (Spring 2024)
- Presented research updates at the lab's biweekly seminars
- Attendee, KORMS–KIIE 2026 Spring Joint Conference, Gyeongju, Korea (Jun 2026)
- Attendee, ACM ICAIF 2025 (International Conference on AI in Finance), Singapore (Nov 2025)

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
  <img src="https://img.shields.io/badge/CVXPY-475569?style=flat-square" alt="CVXPY" />
  <img src="https://img.shields.io/badge/R-276DC3?style=flat-square&logo=r&logoColor=white" alt="R" />
  <img src="https://img.shields.io/badge/LaTeX-008080?style=flat-square&logo=latex&logoColor=white" alt="LaTeX" />
  <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white" alt="TensorFlow" />
  <img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white" alt="Streamlit" />
  <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white" alt="Git" />
</p>

<br />

## 📂 Repositories

**Quantitative Finance**

| Repository | Description |
|---|---|
| [dmfm-kospi](https://github.com/Woominju/dmfm-kospi) | Deep Multi-Factor Model with graph-based industry/market neutralization on 934 KOSPI stocks (team project) |
| [smote-feature-importance-stability](https://github.com/Woominju/smote-feature-importance-stability) | Walk-forward credit-default study: SMOTE lowered AUROC in all 36 runs and reshuffled feature importances (team project) |
| [credit-risk-analysis](https://github.com/Woominju/credit-risk-analysis) | How one IQR clipping rule erased the strongest feature in a loan-approval model (test accuracy 0.65 → 0.79) |

**Time Series & Evaluation**

| Repository | Description |
|---|---|
| [PWTA](https://github.com/Woominju/PWTA) | Undergraduate thesis: re-evaluating time-series anomaly detectors under raw point-level PR-AUC |
| [paper-implementations](https://github.com/Woominju/paper-implementations) | Small implementations of papers I read (e.g. worst-case robust portfolios as a cone program, Anomaly Transformer), linked to my Notion notes |
| [simpsons-paradox-regression](https://github.com/Woominju/simpsons-paradox-regression) | Simulation of a regression slope that flips sign when a correlated variable is controlled for |

<details>
<summary><b>Coursework & practice</b></summary>
<br />

| Repository | Description |
|---|---|
| [deep-learning-coursework](https://github.com/Woominju/deep-learning-coursework) | Deep learning class assignments (2023) |
| [streamlit-dashboard](https://github.com/Woominju/streamlit-dashboard) | Streamlit and Plotly dashboard practice |
| [heart-disease-ann](https://github.com/Woominju/heart-disease-ann) | ANN for heart disease prediction |
| [hotel-reservation-dataset](https://github.com/Woominju/hotel-reservation-dataset) | Hotel booking cancellation data |
| [smiling-face-cnn](https://github.com/Woominju/smiling-face-cnn) | CNN for smiling vs. non-smiling faces |
| [logic-and-programming](https://github.com/Woominju/logic-and-programming) | Python and pandas exercises |
| [git-conflict-practice](https://github.com/Woominju/git-conflict-practice) | Git branching and merge conflict practice |

</details>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f172a,55:1e3a8a,100:3b82f6&height=110&section=footer" alt="" width="100%" />
</p>
