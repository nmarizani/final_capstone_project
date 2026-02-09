# Ruvimbo: Maternal Health Monitoring System

An **integrated AI solution** combining clinical data analysis, machine learning (MLP/CNN), and hardware prototyping to detect and manage **Postpartum Hemorrhage (PPH) risk**.  

Link to video presentation 

## Table of Contents

- Data Analysis & Transformation 
- Data Cleaning & Feature Engineering
- Model Training & Integration
- Hardware & UI Prototyping
- Installation & Setup
- References

## Data Analysis & Transformation

**Source Data:** Baseline maternal health records focused on physiological and demographic vitals.  

**Localization (Zimbabwe Cohort):** Transformed the original South Asian dataset into a high-fidelity Zimbabwe-specific cohort using statistical rescaling.  

**Anemia Modeling:** Applied Bayesian adjustments to achieve a target **31% anemia prevalence**.  

**Physiological Shifts:** Adjusted Blood Pressure (SBP/DBP) baselines to reflect higher regional stress factors.  

**Demographics:** Rescaled **Age** and **Parity** (Poisson distribution) to match Sub-Saharan African maternal profiles.  

## Data Cleaning & Feature Engineering

**Standardization:** Implemented z-score normalization for **age, BMI, and vital signs** to ensure model stability.  

**Signal Processing:** Analyzed **PPG (Photoplethysmogram)** data in the frequency domain, filtering for the **1–3 Hz Cardiac Band (60–180 bpm)** to eliminate noise.  

**Labeling:** Categorized patient states into:  
- **Normal**  
- **Masking**  
- **Decompensation**  

based on heart rate trends during obstetric emergencies.  

## Model Training & Integration

**MLP (Multi-Layer Perceptron):** Trained on **tabular clinical features** (Hemoglobin, BP, BMI) to predict baseline PPH risk.  

**CNN (Convolutional Neural Network):** Utilized for **real-time PPG signal analysis**, detecting morphology shifts in heart rate that precede critical clinical failure.  

**Hybrid Logic:** The models feed a triage system:  

| Status   | Indicator | Action |
|----------|-----------|--------|
| Normal   | Green     | Stable vitals |
| Warning  | Yellow    | Masking phase; recheck in 5 minutes |
| Critical | Red       | Decompensation; triggers immediate alarm |

## Hardware & UI Prototyping

**Tinkercad Simulation:** Developed an **Arduino-based prototype** using an LDR sensor, LCD, and Buzzer to simulate live patient monitoring.  
Link to Design simulation: https://www.tinkercad.com/things/h7RhB6euBB6-dazzling-kup/editel?returnTo=%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=DE9olHCSR-mMSFoHcx5vihOplyp_ydOTbkNDKp-06Vw

**Figma Dashboard:** Designed a high-fidelity UI using a **Magenta-500 (#ff22f0)** branding palette, featuring live scan screens and critical notification flows.
Link to Figma design: https://www.figma.com/design/JSrNt7PvEl8tJOwuf2zrc2/Ruvimbo-Motherhood-Dashboard?node-id=0-1&t=9iezWi4itYgp1Qgc-1

## Installation & Setup

# Clone the repository
git clone https://github.com/nmarizani/final_capstone_project.git

cd final_capstone_project

# Install dependencies
pip install -r requirements.txt

# Run data preprocessing
run code cells in notebook

## References
UCI Machine Learning Repository. (2023). Archive.ics.uci.edu. https://archive.ics.uci.edu/dataset/863/maternal+health+risk