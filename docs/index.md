# Federated Learning for Postoperative Segmentation of Treated glioblastoma (FL-PoST)

## Announcement

**Duke University**, **Indiana University**, and the [Response Assessment in Neuro-Oncology (RANO)](https://doi.org/10.1093/nop/npv037) team are excited to announce a new collaborative study seeking to extend the FeTS initiative to the post-operative/post-treatment setting using a large, diverse imaging dataset derived from patients with previously treated glioblastoma, which is hereby termed **Federated Learning for Postoperative Segmentation of Treated glioblastoma (FL-PoST)** or simply **FeTS 2.0**. 

The **FL-PoST** initiative aims to revolutionize the quantification of brain tumors by establishing an international federation of healthcare institutions and developing an open-source software ecosystem that offers simple, automated, and accurate tumor segmentation free from inter-reader variability.

If you have previously been a part of the [**preoperative FeTS** initiative](https://www.nature.com/articles/s41467-022-33407-5), thank you for your continued interest and support! We hope that you will consider participating **FL-PoST** as well.

## Purpose of the study

- Extend the FeTS initiative for automated MRI segmentation of patients with previously treated glioblastoma. 
- The FL-PoST model will allow quantitative longitudinal volumetric assessment of glioblastoma MRI subregions in the post-treatment follow up setting, which is the most common setting for obtaining brain MRI in these patients. 
- We further plan to validate the FL-PoST model using clinical trial data with expert consensus RANO assessments.


## How to participate

1.	Identify a cohort of brain tumor MRI scans from your institution with a confirmed initial diagnosis of glioblastoma (this is the most important step and can start as soon as possible!).
2.	Identify relevant series (T1, T1+Gd, T2, T2-FLAIR) for each subject and their respective post-operative follow-up scans.
3.	Identify a "technical point of contact", who will conduct the data processing and experiment from your end.
4.	Download and install the [FeTS software](https://github.com/FeTS-AI/Front-End) (detailed instructions along with a new installer is coming soon!).
5.	Preprocess the MRI data using the [FeTS software](https://github.com/FeTS-AI/Front-End) (detailed instructions along with a new installer is coming soon!).
6.	Generate automated segmentations using pre-trained models.
7.	Manually annotate and correct the automated tumor segmentations to generate ground truth labels using the tool of your choice (we recommend [ITK-SNAP](http://www.itksnap.org/pmwiki/pmwiki.php), [CaPTk](https://www.med.upenn.edu/cbica/captk/), or [3D-Slicer](https://www.slicer.org/)). **Please** ensure that the generated labels are silhouettes (i.e., the entire volume of the tumors are delineated) and not just boundaries.
8.	Run the federated training during the specified 2-week training window (to be announced).


## Requirements for participation

### Hardware
- Image processing computer
- Internet connection
- ~100-500 GB free disk space (depending on # of studies)
- GPU with 12+ GB of VRAM

###	Software/OS
- Linux
- Windows


### Dataset
-	Brain MRI scans obtained from any manufacturer/model/field strength of scanner
-	Confirmed initial diagnosis of glioblastoma.
-	T1 (pre-contrast), T1 (Gd post-contrast), T2, and T2-FLAIR volumes available (each preferably with axial or full 3D scan).
-	Longitudinal patient assessments (3 or more post-op MRIs preferred per patient).
-	Minimum suggested cohort of 40 patients (120 scans total).


## Expected study timeline

- We anticipate that datasets will be compiled by sites during **July/August 2023** and annotated throughout **August-November**. 
- The goal is to have processed, annotated datasets ready to train by the start of the [Society for Neuro-Oncology (SNO) annual meeting](https://sno2023.eventscribe.net/) on **15th November, 2023**.


## Benefits to participating

- In addition to contributing to the advancement of tumor segmentation technology, participating site staff will be eligible to be included as co-authors on related publications as well as acknowledged on the [FeTS website](http://www.fets.ai/), if desired. 
- Please see the publication from the [pre-operative FeTS study](https://www.nature.com/articles/s41467-022-33407-5), which was recently published in Nature Communications. In addition, participants will have early access to the FL-Post segmentation model before it is made publicly available.

## Where to sign up

If interested, please complete the following survey and a member of the study team will reach out with any next steps: [redcap.duke.edu/redcap/surveys/?s=RDXFYPTWA8CDKWFH](https://redcap.duke.edu/redcap/surveys/?s=RDXFYPTWA8CDKWFH)

## More information?

- FL-Post Website: [fets-ai.github.io/FL-PoST](https://fets-ai.github.io/FL-PoST/)
- For more information about the FeTS initiative: [www.fets.ai](https://www.fets.ai/)

The FL-PoST software is still being finalized. If you sign up to participate in the study, we will send information on installing the software as soon as it is ready. Suggested annotation tools:
-	[ITK-SNAP](http://www.itksnap.org/pmwiki/pmwiki.php)
- [CaPTk](https://www.med.upenn.edu/cbica/captk/)
- [3D-Slicer](https://www.slicer.org/)

If you have any additional questions, please feel free to reach out to: [admin [at] fets.ai](mailto:admin@fets.ai)


## People
 
- The FL-PoST (FeTS 2.0) Study Team
- Sarah Cubberley, Duke University (study coordinator)
- Spyridon Bakas, University of Pennsylvania (study organizer)
- Evan Calabrese, Duke University (study lead)

