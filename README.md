# Quaoar Repository

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

```

---

## 1. Occultations Data (`/occultations`)

This folder contains the astrometric projections of the stellar occultation chords onto the sky plane. The files are numbered from `01` to `37`, corresponding to 37 distinct occultation events.

### Column Description for Occultation Files

All text files within the `occultations` directory (`_pos_`, `_err_`, and `_neg_`) follow the same 6-column structure, separated by whitespace.

| Column | Description | Unit / Format | Example |
| --- | --- | --- | --- |
| **1** | **$f$ coordinate** (sky-plane position) | Kilometers (km) | `555.397` |
| **2** | **$g$ coordinate** (sky-plane position) | Kilometers (km) | `62.276` |
| **5** | **Time** of the event | Julian Date (JD) | `2458753.29348219` |
| **6** | **Identifier String** (Station + Event Type) | String | `Otjozondjupa_immersion` |

#### Identifiers Breakdown (Column 6):

* **Positive files (`_pos_`):** The string ends with `_immersion` (star disappears) or `_emersion` (star reappears).


* **Error files (`_err_`):** The string ends with `_err-` or `_err+`, representing the lower and upper bounds of the chord uncertainty.


* **Negative files (`_neg_`):** The string ends with `_start` or `_end`, marking the observational window limits along the track where the star was monitored but not occulted.



**Example of data rows (from a positive detection):**

```text
  555.397     62.276  -5.82   3.89 2458753.29348219 Otjozondjupa_immersion
 -149.814    533.286  -5.82   3.89 2458753.29488479 Otjozondjupa_emersion

```

### Event Log Mapping

The numbering in the filenames (`01` to `37`) corresponds to the following observation dates:

| ID | Date (UTC) | ID | Date (UTC) | ID | Date (UTC) |
| --- | --- | --- | --- | --- | --- |
| **01** | 2019-03-27 06:57 | **14** | 2018-07-26 15:03 | **27** | 2013-07-09 02:41 |
| **02** | 2019-04-28 06:46 | **15** | 2023-07-15 00:16 | **28** | 2024-05-29 19:15 |
| **03** | 2019-05-28 23:40 | **16** | 2023-08-24 03:22 | **29** | 2011-02-11 10:05 |
| **04** | 2019-06-05 03:00 | **17** | 2024-04-10 03:55 | **30** | 2019-06-28 12:35 |
| **05** | 2019-08-04 17:24 | **18** | 2018-09-02 18:16 | **31** | 2025-06-20 23:46 |
| **06** | 2019-09-26 18:55 | **19** | 2022-06-24 12:09 | **32** | 2025-06-12 09:53 |
| **07** | 2019-10-16 01:38 | **20** | 2020-06-11 16:30 | **33** | 2025-07-04 23:06 |
| **08** | 2020-06-16 08:38 | **21** | 2024-07-04 22:57 | **34** | 2025-08-28 02:43 |
| **09** | 2020-07-01 21:38 | **22** | 2023-08-01 22:18 | **35** | 2025-08-28 02:44 |
| **10** | 2022-08-09 06:34 | **23** | 2023-05-20 00:24 | **36** | 2025-08-31 13:46 |
| **11** | 2011-05-04 02:38 | **24** | 2023-05-24 14:36 | **37** | 2024-08-28 10:38 |
| **12** | 2023-05-13 08:40 | **25** | 2012-02-17 04:30 |  |  |
| **13** | 2023-05-26 15:53 | **26** | 2012-10-15 00:41 |  |  |

---

## 2. Rotational Light Curves (`/rotation`)

This folder contains the photometric data used to extract Quaoar's rotational amplitude and period. These datasets are fitted simultaneously with the occultation chords within the MCMC framework.

### 2003 Photometry (`quaoar_2003.txt`)

This is a comma-separated file containing the ground-based observations from 2003. It includes a header with two columns:

1. **`time`**: The mid-exposure time of the image, provided in Julian Date (JD).


2. **`mag`**: The measured target flux (relative photometry).



### Hubble Space Telescope Photometry (`HST.txt`)

This is a comma-separated file containing the photometry extracted from the HST images. It does not contain a header, but the 13 columns are strictly ordered as follows:

| Column | Name | Description |
| --- | --- | --- |
| **1** | `jd` | Mid-exposure time of the observation in Julian Date |
| **2** | `ABmag` | AB Magnitude |
| **3** | `ABmag_err` | Error of the AB Magnitude |
| **4** | `STmag` | ST Magnitude |
| **5** | `flux` | Raw target flux |
| **6** | `snr` | Signal-to-Noise Ratio |
| **7** | `filter` | HST Filter used (e.g., F350LP) |
| **8** | `center_x` | Target center X pixel coordinate |
| **9** | `center_y` | Target center Y pixel coordinate |
| **10** | `ap_pix` | Photometric aperture radius (in pixels) |
| **11** | `center_ra` | Right Ascension (RA) of the target center |
| **12** | `center_dec` | Declination (Dec) of the target center |
| **13** | `ap_arcsec` | Photometric aperture radius (in arcseconds) |

---

## 3. Ephemerides (`/ephem`)

The reference ephemeris files used in our calculations are provided.

* **`de440.bsp`**: The standard JPL Planetary Ephemeris (DE440).
* **`50000_Quaoar_nima_v19l.bsp`**: The specific state vectors and ephemeris generated for (50000) Quaoar.

