# West Bengal Election Prediction Model (2021 → 2026)

## Contributors

<a href="https://github.com/aam-007/bengal-election-2026/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=aam-007/bengal-election-2026" />
   <img src="https://contrib.rocks/image?repo=laithshaikh/bengal-election-2026" />
   <img src="https://contrib.rocks/image?repo=soham21sahay/bengal-election-2026" />
</a>

## Overview

This project is a data-driven analysis and prediction of the **2026 West Bengal Legislative Assembly elections** using the 2021 constituency-level results. The goal is to create a systematic model to forecast likely winners and party performance, incorporating historical data and basic constituency features.

---

## Project Structure

```
project/
│
├── 01_data_cleaning.ipynb                      # Phase 1: Data cleaning and preprocessing
├── 02_constituency_results.ipynb               # Phase 2: Constituency-level winner analysis
├── 03_party_state_aggregation.ipynb            # Phase 3: Party and state-level summaries
├── 04_feature_analysis.ipynb                   # Phase 4: Feature selection and exploration
├── 05_model_training.ipynb                     # Phase 5: Model training and evaluation
├── 06_prediction_2026.ipynb                    # Phase 6: 2026 prediction, visualizations, and export
├── raw_2021.csv                                # Original 2021 election data
├── clean_2021.csv                              # Cleaned 2021 data
├── constituency_results_2021.csv               # Processed constituency results
├── party_summary_2021.csv                      # All-India party summary
├── state_party_summary_2021.csv                # State-wise party summary
├── constituency_predictions_2021_filtered.csv  # Model predictions on 2021 data
└── README.md                                   # Project documentation
```

---

## Data Description

The project uses the **2021 West Bengal election dataset** from the Election Commission of India (ECI), which includes:

| Column Name       | Description                                      |
|-------------------|--------------------------------------------------|
| STATE/UT NAME     | State or union territory                         |
| AC NO.            | Assembly constituency number                     |
| AC NAME           | Name of the constituency                         |
| CANDIDATE NAME    | Candidate name                                   |
| SEX               | Candidate gender                                 |
| AGE               | Candidate age                                    |
| CATEGORY          | Candidate category (General/SC/ST)               |
| PARTY             | Political party                                  |
| GENERAL           | Votes received in general ballots                |
| POSTAL            | Votes received in postal ballots                 |
| TOTAL             | Total votes received                             |
| % VOTES POLLED    | Percentage of votes polled                       |
| TOTAL ELECTORS    | Total registered voters                          |

---

## Phases

### Phase 1: Data Cleaning
- Load raw CSV data
- Identify and promote headers
- Normalize column names
- Convert numeric fields
- Standardize text columns
- Extract candidate numbers and names

**Output:** `clean_2021.csv`

---

### Phase 2: Constituency-Level Analysis
- Sort candidates by total votes per constituency
- Identify winners and runners-up
- Calculate vote margins and vote shares

**Output:** `constituency_results_2021.csv`

---

### Phase 3: Party and State-Level Aggregation
- Summarize seats won and vote share per party (all India)
- Summarize seats won per party at state level
- Include runner-up information

**Outputs:** `party_summary_2021.csv`, `state_party_summary_2021.csv`

---

### Phase 4: Feature Exploration
Select key predictive features:
- Total votes polled
- Number of candidates
- Vote margin
- Winner and runner-up vote shares
- Filter parties with sufficient representation for modeling

---

### Phase 5: Model Training and Evaluation
- Encode party labels
- Train Random Forest classifier on filtered 2021 data
- Evaluate accuracy and generate classification report
- Predict party winners for all 2021 constituencies (filtered)

**Output:** `constituency_predictions_2021_filtered.csv`

---

### Phase 6: Predict 2026 Election Results
- Use the trained model to forecast 2026 winners using 2021 constituency features
- Generate visualizations:
  - Bar charts of predicted seats per party
  - Vote share distributions
- Export predictions and plots

**Outputs:**
- Predicted constituency winners for 2026
- Visual charts and summary tables

---

## Key Findings

- The model achieves approximately **78% accuracy** on test data.
- Predicted seat count for major parties in 2026 (example):
  - **AITC:** 225 seats
  - **BJP:** 77 seats
- Visualizations provide insight into state-wise distribution and vote share trends.

---

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/aam-007/bengal-election-2026.git
   cd bengal-election
   ```

2. Ensure all required CSV files are present.

3. Run Jupyter notebooks sequentially from Phase 1 to Phase 6:
   ```bash
   jupyter notebook
   ```

4. Review outputs and visualizations generated in each phase.

---

## Requirements

- Python 3.x
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

Install dependencies:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```

---

## Notes

- The model uses **only the 2021 dataset**.
- Predictions assume that historical patterns and constituency features remain relevant for 2026.
- Visualizations and CSV exports help interpret and present results professionally.

---

Created By:
-Aditya Mishra
-Laith Shaikh
-Soham Sahay

## Acknowledgments

- Election Commission of India (ECI) for providing the 2021 election data
- The open-source community for the tools and libraries used in this project
