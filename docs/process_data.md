# Processing the Data for FeTS

## Data Requirement

- Brain MRI scans obtained from any manufacturer/model/field strength of scanner.
- Confirmed initial diagnosis of glioblastoma.
- Longitudinal patient assessments (3 or more post-op MRIs preferred per patient).
- Minimum suggested cohort of 40 patients (120 scans total).
- Required modalities per time-point (each preferably with axial or full 3D scan):
  - T1-weighted pre-contrast (T1): pre-contrast
  - T1-weighted post-contrast (T1Gd): Gd post-contrast
  - T2-weighted (T2)
  - T2 Fluid Attenuated Inversion Recovery (T2-FLAIR)

## Data Arrangement

Each subject's DICOM (or NIfTI) image is to be put in a separate folder:
```
Input_Data
│
└───Patient_001
│   │
│   └───Timepoint_001
│   │   │
│   │   └───T1
│   │   │   │ image_001.dcm
│   │   │   │ image_002.dcm
│   │   │   │ ...
│   │   └───T1GD
│   │   │   │ image_001.dcm
│   │   │   │ image_002.dcm
│   │   │   │ ...
│   │   └───T2
│   │   │   │ image_001.dcm
│   │   │   │ image_002.dcm
│   │   │   │ ...
│   │   └───T2FLAIR
│   │   │   │ image_001.dcm
│   │   │   │ image_002.dcm
│   │   │   │ .....
│   │
│   └───Timepoint_002
│   │   │
│   │   └───T1
│   │   │   │ image_001.dcm
│   │   │   │ image_002.dcm
│   │   │   │ ...
│   │   └───T1GD
│   │   │   │ image_001.dcm
│   │   │   │ image_002.dcm
│   │   │   │ ...
│   │   └───T2
│   │   │   │ image_001.dcm
│   │   │   │ image_002.dcm
│   │   │   │ ...
│   │   └───T2FLAIR
│   │   │   │ image_001.dcm
│   │   │   │ image_002.dcm
│   │   │   │ .....
│   │
│   └───Timepoint_N
│   
└───Patient_JohnDoe
│   │
│   └───Timepoint_001
│   │ ...   
│   │
│   └───Timepoint_002
│   │ ...   
│   
│ ...   
│   
└───Patient_SmithJoe
│   │ ...
```
- Ensure that unexpected "special" string characters that could hamper the file system's processing are not present (read [this article](https://www.mtu.edu/umc/services/websites/writing/characters-avoid/#:~:text=Illegal%20Filename%20Characters) for more details). Some examples of this include (and are not limited to): `!`, `@`, `#`, `$`, `%`, `^`, `&`, `*`, `'`, `;`, `:`, `,`, `~`
- Please note that subject IDs should be **unique strings** and can be parsed by code. Some examples of problematic and acceptable subject IDs are as follows:
  - **Problematic**: "Patient_1", "Patient_2", ..., "Patient_10", ...,"Patient_20", ...,"Patient_100"
  - **Acceptable**: "Patient_001", "Patient_002", ..., "Patient_010", ..., "Patient_020", ..., "Patient_100", ...


[Back To Top &uarr;](#table-of-contents)
---
[Next: Run Application](./runningApplication.md)

---
