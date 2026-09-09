# Quaoar Triaxial Shape and Dynamics Data Repository

This repository contains the data used for the analyses presented in the manuscript *"Ellipsoidal Modeling Framework for TNOs: the triaxial shape of (50000) Quaoar and its implications for Weywot and the dynamical environment"*. 

The data is organized into two main directories: `occultations` (containing multi-chord stellar occultation profiles) and `rotation` (containing photometric light curves).

## Repository Structure

```text
├── occultations/
│   ├── occ_50000_Quaoar_pos_*.txt  (Positive detection chords)
│   ├── occ_50000_Quaoar_err_*.txt  (Uncertainties for positive detections)
│   └── occ_50000_Quaoar_neg_*.txt  (Negative detection chords)
└── rotation/
    ├── HST_1_3_4_5.txt             (Hubble Space Telescope photometry)
    └── quaoar_rot_giuliano.txt     (2003 photometry data)
