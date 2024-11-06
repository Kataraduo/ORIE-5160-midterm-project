# ORIE-5160 Midterm Project: HeartSteps Analysis
This repository contains the code, data processing scripts, and analysis for our project on how framing styles in behavior change notifications influence physical activity levels. Specifically, we compare "Active" versus "Sedentary" notifications and explore the role of baseline self-efficacy in moderating the effectiveness of these frames.

## Project Overview
Our project analyzes data from the HeartStepsV1 randomized controlled trial, which aimed to encourage physical activity through contextually tailored notifications. Using Google Fit and Jawbone step counts recorded 30 and 60 minutes after notifications, we assessed the effects of framing styles on activity levels.

## Dataset

The **HeartStepsV1** dataset comes from a randomized controlled trial evaluating just-in-time adaptive interventions for physical activity. It includes step counts from the Jawbone tracker and Google Fit, as well as notifications encouraging either "active" or "sedentary" behavior. We are analyzing user responses based on these suggestions and investigating how user location and self-efficacy influence these outcomes.

For more information, see the original dataset on GitHub: [HeartStepsV1 Dataset](https://github.com/klasnja/HeartStepsV1).


## Problem Statement
We aim to answer the following research questions:
- **Primary Question:** How does the framing of activity suggestions (Active vs. Sedentary) impact physical activity, measured through step counts 30 and 60 minutes after notification?
- **Exploratory Question:** Does baseline self-efficacy moderate the impact of framing styles on physical activity?

## Key Findings
- "Sedentary" notifications led to a statistically significant increase in Google Fit step counts at 60 minutes post-notification, suggesting a potential effect of framing style.
- The effect was not observed in 30-minute post-notification data or in Jawbone measurements, indicating device and time-specific differences.
- Baseline self-efficacy showed no significant moderating effect, though a marginal interaction was observed in log-transformed data.

## Methodology (PCS Framework)
- **Dataset:** We used the HeartStepsV1 dataset, consisting of Google Fit and Jawbone step count data, notifications, and user demographics collected over six weeks for 37 participants.
- **Framework:** Our analysis follows the Predictability, Computability, and Stability (PCS) framework to ensure that results are robust and generalizable.
- **Data Cleaning:** Data was filtered to exclude outliers and ensure reasonable step counts. Inconsistencies in self-efficacy scores were addressed by reverse-coding.
- **Analysis:** We applied a Generalized Linear Mixed Model (GLMM) with a negative binomial distribution due to zero-inflated data. Log transformations were also used to assess data normality.

## Repository Structure
```
ORIE-5160-midterm-project/
│
├── data/
│   ├── gfsteps.csv          # Google Fit step data
│   ├── jbsteps.csv          # Jawbone tracker step data
│   ├── suggestions.csv      # Activity suggestions and context data
│   ├── users.csv            # User demographics and survey data
│   ├── mydata_steps_gf_py.csv  # Dataset generated during cleaning and preprocessing
│   └── steps_notif_users_py.csv   # Dataset generated during cleaning and preprocessing       
│
├── dslc_documentation/
│   ├── 01_cleaning_v2.ipynb    # Data cleaning steps (partial)
│   └── main_code.ipynb         # Full code
│
├── figure/
│   ├── hist_totalday.png      # All the figures generated during the analysis 
│   └── ...
│
│
└── README.md

```



## Results and Discussion
The primary findings suggest that "Sedentary" notifications may increase physical activity within specific timeframes and contexts. The PCS framework helped reveal the influence of computational and device-specific choices on stability and generalizability.

## Limitations
- **Sample Size:** The small sample (N=25) limited the power to detect subtle effects and may have increased Type II error.
- **Device Differences:** Variability between Google Fit and Jawbone highlights the importance of cross-device validation.
- **Duration:** The six-week trial may not be sufficient to capture long-term behavior changes.


## GitHub Repository
Collaborate with us on this project: [GitHub Repository Link](https://github.com/Kataraduo/ORIE-5160-midterm-project.git)

## Acknowledgments
We thank Prof. Raaz Dwivedi and our TA Kyuseong Choi for their insightful feedback and guidance throughout this project.