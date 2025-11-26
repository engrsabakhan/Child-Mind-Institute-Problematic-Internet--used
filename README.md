<b>📘 Child Mind Institute — Problematic Internet Use (PIU)</b>

Predicting PIU scores in children using physical fitness, demographics, and accelerometer time-series.
***
<b>🧭 Overview</b>

This project builds a machine-learning pipeline to predict the SII score, an indicator of Problematic Internet Use, using structured data and wearable sensor data.
It is based on the Kaggle competition:

<i>🔗 https://www.kaggle.com/competitions/child-mind-institute-problematic-internet-use</i>

***


<b>📑 Table of Contents</b>

<pre>
🌟 Objectives

📦 Dataset

🗂️ Repository Structure

🧹 Data Preparation

🏗️ Feature Engineering

🤖 Modeling

📊 Results

⚠️ Limitations

🚀 Future Work

📝 License

📚 References

</pre>

***
<b>🌟 Objectives</b>

Predict SII (0–3) using survey, physical, and actigraphy data.

Understand relationships between activity/sleep and internet behavior.

Create a reproducible ML workflow: EDA → Processing → Modeling → Evaluation.

Benchmark multiple ML models and ensembles.

Produce a clean, competition-ready pipeline.
***
<b>📦 Dataset</b>

📁 Files Provided

<i>train.csv, test.csv, sample_submission.csv

series_train.parquet/id=XX/*.parquet (accelerometer)

series_test.parquet/id=XX/*.parquet</i>
***
<b>🎯 Target</b>

<i>SII Score — categorical scale from 0 → 3
(indicating problematic internet use severity)</i>

***
<b>🗂️ Repository Structure</b>

<pre>
  .
├── Dataset/
│   └── Dataset link.txt
├── Notebook/
│   └── child_mind.py
├── References/
│   └── data dictionary.pdf
├── Requirements.txt
├── LICENSE
└── README.md

</pre>
***
<b>🧹 Data Preparation</b>

🟦 Tabular Data</i>

<i>Standardization

Handling missing values

Outlier detection

Encoding categorical features

Scaling physical metrics</i>

🟩 Time-Series (Actigraphy)

<i>Loading participant-wise parquet files

Non-wear detection

Aggregated per-user features:

Mean/Std

Skewness/Kurtosis

ENMO (activity proxy)

Daily movement/sleep indicators</i>

➡️ All extracted features merged into final training table.

***

<b>🏗️ Feature Engineering</b>

1.BMI, waist ratios, BIA features

2.Internet use hours/day

3.Activity intensity patterns

4.Sleep efficiency indicators

5.Percentile-based movement metrics

6.Model-based feature importance for selection
***
<b>🤖 Modeling</b>

✔️ Approaches Tried

<i>LightGBM

XGBoost

CatBoost

Voting Ensemble</i>

✔️ Training Strategy

<i>5-fold stratified CV

Out-of-fold predictions

Threshold tuning for best ordinal classification</i>
***
<table style="border-collapse: collapse; width: 100%; max-width: 800px; font-family: Arial, Helvetica, sans-serif;">
  <thead>
    <tr>
      <th style="border: 1px solid #ddd; padding: 8px; text-align: left; background:#f3f4f6;">Model</th>
      <th style="border: 1px solid #ddd; padding: 8px; text-align: right; background:#f3f4f6;">Accuracy</th>
      <th style="border: 1px solid #ddd; padding: 8px; text-align: right; background:#f3f4f6;">Precision</th>
      <th style="border: 1px solid #ddd; padding: 8px; text-align: right; background:#f3f4f6;">Recall</th>
      <th style="border: 1px solid #ddd; padding: 8px; text-align: right; background:#f3f4f6;">F1-Score</th>
      <th style="border: 1px solid #ddd; padding: 8px; text-align: right; background:#f3f4f6;">Cohen Kappa</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="border: 1px solid #ddd; padding: 8px;">CatBoost</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.3289</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.34</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.33</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.325</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.10</td>
    </tr>
    <tr>
      <td style="border: 1px solid #ddd; padding: 8px;">XGBoost</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.4066</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.41</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.40</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.40</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.16</td>
    </tr>
    <tr>
      <td style="border: 1px solid #ddd; padding: 8px;">LightGBM</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.4794</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.48</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.48</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.47</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.21</td>
    </tr>
    <tr style="font-weight: 700; background:#f9fafb;">
      <td style="border: 1px solid #ddd; padding: 8px;">Voting Ensemble</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.5474</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.5946</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.5474</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.5387</td>
      <td style="border: 1px solid #ddd; padding: 8px; text-align: right;">0.3465</td>
    </tr>
  </tbody>
</table>
***
