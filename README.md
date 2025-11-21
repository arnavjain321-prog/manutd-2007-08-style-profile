# Manchester United 2007/08 – Attacking Unit Analysis

This project analyzes the attacking profiles of Manchester United’s forwards during the 2007/08 Premier League season.  
The goal is to quantify roles, shot volume, finishing efficiency, and off-ball contribution using FBref-derived data.

---

## Dataset

All datasets were manually exported from FBref and include:

- `manutd_2007_08_playing_time.csv`
- `manutd_2007_08_shooting.csv`
- `manutd_2007_08_misc.csv`
- `manutd_2007_08_matches_raw.csv`

Only real, available stats were used; unavailable metrics (e.g., detailed passing, xA, progressive passes) were intentionally excluded.

---

## Focused Player Group (Attackers)

- Cristiano Ronaldo  
- Wayne Rooney  
- Carlos Tevez  
- Ryan Giggs  
- Nani  

Primary analysis centers on **Ronaldo, Rooney, and Tevez**.

---

## 1. Data Cleaning & Preparation

We:

- Loaded raw FBref tables from `data/raw/`
- Cleaned column names, formats, and units
- Filtered players by attacking positions (FW, WF, AM)
- Merged playing time, shooting, and misc tables
- Constructed per-90 metrics for all relevant actions:
  - Goals per 90  
  - Shots per 90  
  - Shots on target per 90  
  - Goal conversion  
  - Defensive actions per 90 (tackles won, interceptions, fouls drawn)

The merged per-attacker DataFrame is the foundation for all visuals in `02_attack_profile.ipynb`.

---

## 2. Shot Volume Analysis

### Shots per 90

A bar chart of shots per 90 highlights:

- Ronaldo leading the team at roughly 3 shots per 90  
- Rooney and Tevez forming a second tier (~1.8–2.2 shots per 90)  
- Nani and Giggs contributing situationally rather than as primary shooters  

This reflects Ferguson’s attacking structure:  
Ronaldo served as the primary finisher, with Rooney and Tevez acting as hybrid creator-scorers.

---

## 3. Shot Volume vs Finishing Efficiency

A scatterplot compares:

- **Shots per 90** (shot volume)  
- **Goal conversion** (goals per shot)

Findings:

- Ronaldo combines elite volume with strong finishing  
- Tevez shows efficient finishing at moderate volume  
- Rooney is heavily involved in chance creation with slightly lower conversion  
- Saha (limited minutes) appears as an extremely efficient finisher  

This visualization clearly separates role and efficiency among the forwards.

---

## 4. Multi-Player Radar: Ronaldo vs Rooney vs Tevez

A normalized radar chart compares the three main forwards across:

- Goals per 90  
- Shots per 90  
- Shots on target per 90  
- Goal conversion  
- Defensive actions per 90  
- Fouls drawn per 90  
- Crosses per 90  

Interpretation:

- **Cristiano Ronaldo** dominates almost every attacking axis with strong defensive contribution.  
- **Wayne Rooney** shows a broad two-way profile: pressing, defensive work, and link play.  
- **Carlos Tevez** balances finishing quality with high work rate and off-ball aggression.

Their profiles complement each other within the same front line.

---

## 5. Visualizations

Below are the main visuals included in this analysis.

### Goals per 90
![Goals per 90 – Manchester United Attackers (2007/08)](plots/goals_per90.png)

### Shots per 90
![Shots per 90 – Manchester United Attackers (2007/08)](plots/shots_per90.png)

### Shot Volume vs Finishing
![Shot Volume vs Finishing – 2007/08 Attackers](plots/volume_vs_conversion.png)

### Radar Profiles — Overlay
![Attacking & Defensive Radar – Ronaldo vs Rooney vs Tevez (2007/08)](plots/radar_three_forwards.png)

### Individual Forward Profiles
![Cristiano Ronaldo – Attacking & Defensive Profile (2007/08)](plots/radar_ronaldo.png)
![Wayne Rooney – Attacking & Defensive Profile (2007/08)](plots/radar_rooney.png)
![Carlos Tevez – Attacking & Defensive Profile (2007/08)](plots/radar_tevez.png)

Each individual radar highlights how their roles differ within the same attacking unit, combining shooting, chance creation, and defensive work.

---

## 6. Individual Player Radars

Separate radars are created for:

- Cristiano Ronaldo  
- Wayne Rooney  
- Carlos Tevez  

Each radar highlights player-specific attributes, such as attacking output, defensive involvement, fouls drawn, and link-up tendencies.

These views help communicate playing style and role to non-technical audiences.

---

## 7. Summary of Findings

Manchester United’s 2007/08 forward line thrived due to clear role specialization:

**Cristiano Ronaldo**  
- Primary scorer and shot leader  
- High-volume attacking focal point  
- Dominant finisher  

**Wayne Rooney**  
- Hybrid forward (creator + presser)  
- High defensive work rate  
- Connects midfield and attack  

**Carlos Tevez**  
- Efficient finisher  
- Relentless presser  
- Constant movement + defensive contribution  

Giggs and Nani added width, crossing, and attacking rotation.

The balance of volume (Ronaldo), work rate (Rooney), and efficiency (Tevez) produced one of the league’s most effective attacking units.
---

## Repository Structure

**data/**
- raw/
  - manutd_2007_08_matches_raw.csv
  - manutd_2007_08_misc.csv
  - manutd_2007_08_playing_time.csv
  - manutd_2007_08_shooting.csv

**notebooks/**
- 02_attack_profile.ipynb

**plots/**
- goals_per90.png
- shots_per90.png
- volume_vs_conversion.png
- radar_three_forwards.png
- radar_ronaldo.png
- radar_rooney.png
- radar_tevez.png

**reports/**
- (placeholder)

**LICENSE**  
**README.md**

---

## How to Run the Analysis

1. **Install dependencies:**
   ```bash
   pip install pandas numpy matplotlib
Open the notebook:

bash
Copy code
jupyter notebook notebooks/02_attack_profile.ipynb
Run all cells to reproduce:

Data cleaning and merging

Per-90 metric engineering

Visualizations (bar charts, scatterplots, radar charts)

Next Steps (Future Work)
Potential extensions include:

Midfield unit analysis (passing, progression, defensive actions)

Defensive unit + goalkeeper profiles

Match-level xG and shot maps

Deploying an interactive dashboard using Streamlit or Dash

Data Source
FBref / StatsBomb

All player-level and match-level statistics (minutes, goals, shots, key passes, defensive actions, etc.) were manually exported from:
https://fbref.com/en/

Data used strictly for educational, non-commercial analysis.

License
This project is released under the MIT License.

Contact
Arnav Jain
Master of Science in Data Science, University of Virginia
LinkedIn: https://www.linkedin.com/in/arnavjain2026/

If you're interested in football-analytics collaboration or opportunities, feel free to reach out.


