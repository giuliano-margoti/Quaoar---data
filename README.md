# Quaoar Triaxial Shape Repository

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

### Column Description for Occultation Files

All text files within the `occultations` directory (`_pos_`, `_err_`, and `_neg_`) follow the same 6-column structure, separated by whitespace.

| Column | Description | Unit / Format | Example |
| :---: | :--- | :--- | :--- |
| **1** | **$f$ coordinate** (sky-plane position) | Kilometers (km) | `555.397` |
| **2** | **$g$ coordinate** (sky-plane position) | Kilometers (km) | `62.276` |
| **5** | **Time** of the event | Julian Date (JD) | `2458753.29348219` |
| **6** | **Identifier String** (Station + Event Type) | String | `Otjozondjupa_immersion` |

#### Identifiers Breakdown (Column 6):
*   **Positive files (`_pos_`):** The string ends with `_immersion` (star disappears) or `_emersion` (star reappears).
*   **Error files (`_err_`):** The string ends with `_err-` or `_err+`, representing the lower and upper bounds of the chord uncertainty.
*   **Negative files (`_neg_`):** The string ends with `_start` or `_end`, marking the observational window limits along the track where the star was monitored but not occulted.

**Example of data rows (from positive detection):**
```text
  555.397     62.276  -5.82   3.89 2458753.29348219 Otjozondjupa_immersion
 -149.814    533.286  -5.82   3.89 2458753.29488479 Otjozondjupa_emersion
