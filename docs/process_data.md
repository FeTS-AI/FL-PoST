# Processing the Data for FeTS

**Note** the `${fets_root_dir}` from [Setup](./setup.md#set-up-the-environment).

## Table of Contents
- [Data Arrangement](#data-arrangement)
- [Running Pre-processing](#pre-processing)
- [Starting from pre-processed data](#starting-from-pre-processed-data)

[Back To Top &uarr;](#table-of-contents)

## Data Arrangement
**Note** the `${fets_root_dir}` from [Setup](./setup.md#set-up-the-environment).

For the first application of FeTS in volumetric brain tumor MRI scans, you should follow the pre-processing pipeline defined in the [International Brain Tumor Segmentation (BraTS) Challenge](http://braintumorsegmentation.org/):
- Download the DICOM files of the structural multi-parametric MRI scans:
  - T1-weighted pre-contrast (T1)
  - T1-weighted post-contrast (T1Gd)
  - T2-weighted (T2)
  - T2 Fluid Attenuated Inversion Recovery (T2-FLAIR)
- Each subject's DICOM (or NIfTI) image is to be put in a separate folder:
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
