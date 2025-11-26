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
