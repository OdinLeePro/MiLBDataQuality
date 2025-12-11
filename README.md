# MiLBDataQuality

MiLBDataQuality is a data-cleaning and validation project built around 2025 Minor League TrackMan pitch by pitch and contact level datasets. The project integrates, cleans, and analyzes two raw data files, producing a combined dataset, error documentation, and calculations such as team level average exit velocities. It emphasizes structured workflows using Excel and Python (Pandas), ensuring data integrity, reproducibility, and baseball specific domain logic.

## Overview

This project was created to accurately merge Minor League TrackMan pitch and contact data from a single 2025 game while identifying and correcting errors in the raw data. The final output is a validated, combined dataset prepared for deeper baseball analytics, such as pitch event sequencing, exit velocity trends, and performance breakdowns.

The workflow includes:

- Cleaning and validating pitch level and contact level TrackMan files  
- Identifying and correcting documented data entry and measurement errors  
- Producing a unified dataset using Python and Pandas  
- Calculating team level average exit velocities  
- Documenting the full process from raw data to final outputs  

## Features

- **TrackMan Data Integration** — Combines pitch and contact datasets using a confirmed one to one merge key (PitchId).
- **Data Cleaning & Quality Control** — Identifies 11 verified errors across both datasets, including:
  - Duplicate PitchIds  
  - Misspelled pitcher/batter names  
  - Incorrect BatterIds  
  - Incorrect Date entry  
  - Impossible velocity and distance measurements  
  - Incorrect team assignment  
  - Negative SpeedDrop values  
- **Descriptive Analytics** — Computes average exit velocities for home and away teams.
- **Reproducible Workflow** — Implemented using Excel and Python (Pandas) through Jupyter Notebook.
- **Documentation** — Includes detailed write ups describing the merge logic, error corrections, and analytical steps.

## Project Structure

```
/MiLBDataQuality
├── Cleaned Data/
│   ├── CombinedData.csv
│   ├── fellowContactCleaned.csv
│   └── fellowPitchCleaned.csv
├── Documents/
│   ├── AvgExitVelo.pdf
│   ├── Errors.pdf
│   └── Process.pdf
├── Raw Data/
│   ├── BBOps_DQ_26FellowContact.csv
│   └── BBOps_DQ_26FellowPitch.csv
├── Analysis.ipynb
├── LICENSE
├── Project Instructions.pdf
├── TeamsData.csv
├── README.md
└── Project Proposal.docx
```

## Data Sources

This project uses TrackMan data from a 2025 Minor League regular season game. Two files were provided:

- **Pitch dataset** — contains every pitch thrown during the game  
- **Contact dataset** — contains all balls put into play or fouled

Baseball knowledge, TrackMan glossary definitions, and validation rules were used to identify and correct inconsistencies.

## Key Outputs

### 1. Combined Dataset
A unified CSV file created using a **left join on PitchId**, ensuring that all pitch events remain included while contact attributes merge where available.

### 2. Average Exit Velocities

Average exit velocities were calculated using only batted balls officially put into play (`PitchCall == "InPlay"`):

- **Home Team (SPR_CAR): 88.06 mph**  
- **Away Team (WIC_SUR): 82.23 mph**

### 3. Error Log (11 Total Errors)

Errors identified across the two datasets include:

- Duplicate PitchIds  
- Incorrect BatterIds  
- Misspelled player names  
- Incorrect batting side  
- Incorrect team assignment  
- Impossible Release Speed (941 mph)  
- Impossible batted ball Distance (752 ft)  
- Incorrect Date entry (2024 instead of 2025)  
- Negative SpeedDrop value  

These errors were corrected or replaced with NULL where appropriate.

## License

This project is licensed under the MIT License.
