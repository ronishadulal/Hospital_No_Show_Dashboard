# Hospital_No_Show_Dashboard
# Healthcare Appointment No-Show Dashboard

An interactive Tableau dashboard analyzing patient no-show patterns at outpatient hospitals in Nepal — built to help hospital administrators identify high-risk appointments and reduce missed-appointment rates through targeted, evidence-based interventions.

## Objective

Outpatient departments in Kathmandu District (Bir Hospital, TUTH, Patan Hospital, NMCTH, and others) face high demand and limited consultation capacity. Missed appointments waste physician time, lengthen waiting periods, and reduce access to care. This dashboard gives OPD managers and hospital administrators a single interactive view to answer:

- What is the overall no-show rate, and how does it trend over the year?
- Do SMS reminders actually reduce no-shows?
- Which appointment types and departments have the highest no-show risk?
- Are repeat no-show patients and long waiting times compounding the risk?
- Does travel distance to the hospital affect attendance?
- What are patients' most common reasons for missing appointments?

## Tools Used

Tableau Public 2025.2 (dashboard build, calculated fields, coordinated views, dashboard actions, interactive filters)

## Dataset

- **Source:** [Nepal Hospital Appointment No-Show Dataset (Kaggle)](https://www.kaggle.com/datasets/ronitmaharjan/nepalhospital-no-show-dataset)
- **Size:** 1,500 rows, 31 variables
- **Variable types:** nominal (hospital, department, appointment type), ordinal (age group, income level, education level), numerical (lead time, waiting time, distance to hospital, previous no-shows), binary (scholarship, SMS received, comorbidities), datetime (scheduled day, appointment day), and geospatial (neighbourhood, distance to hospital)

## Key Findings

- **Overall no-show rate: 24.1%** across 1,500 appointments — roughly 1 in 4 appointments is missed.
- **November has the highest monthly no-show rate (55.0%)** — SMS reminder coverage alone doesn't explain this spike, suggesting other seasonal or operational factors are at play.
- **Lab Review appointments have the highest no-show risk (32.1%)**, followed by Follow-up (24.0%), New Consultation (22.7%), Routine Checkup (22.3%), and Emergency Referral (19.5%).
- **Repeat no-shows compound with wait time:** patients with 2+ prior no-shows *and* 15+ day waits have a **37.6%** no-show rate — more than double the rate for first-time patients with a short wait (19.4%).
- **Distance matters:** longer travel distances are associated with higher no-show rates, pointing to geographic accessibility as a real barrier to care.
- **Personal factors are the most common cited reason for missing appointments** (via treemap of no-show reasons), ahead of healthcare-experience, financial, and transportation barriers.

## Dashboard Design

The dashboard uses a **KPI → trend → risk-driver** layout so administrators can move from a high-level snapshot to root-cause detail without leaving the screen:

1. **KPI cards** — Total Appointments, Overall No-show Rate, Average Waiting Time, Average Distance
2. **Monthly trend line chart** — no-show rate vs. SMS reminder coverage over the year
3. **Horizontal bar chart** — no-show risk by appointment type
4. **Heatmap** — previous no-shows × waiting time, showing compounded risk
5. **Stacked bar chart** — attendance by travel-distance band


Design choices followed established visualization principles rather than default chart settings: position/length encodings over angle/area  a colour-blind-safe blue–orange palette, minimal chart borders/gridlines (Tufte's data-ink ratio), and Gestalt grouping (proximity, similarity, continuity) to keep related KPIs and charts visually linked.


## Limitations

- Correlational, not causal — the dataset lacks socioeconomic status, transportation access, weather, and clinical severity, all of which plausibly affect attendance.
- Single-snapshot data from a limited set of hospitals; findings shouldn't be generalized to all of Nepal's healthcare system without further validation.
- No predictive modeling — this is a descriptive/exploratory dashboard, not a no-show risk classifier. Adding one (e.g., logistic regression) is a natural next step.

