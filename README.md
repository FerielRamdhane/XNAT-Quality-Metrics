## What is this repository for?
This repository is about the Image processing containers developped at the Eurobioimaging MED-Hub for the XNAT platform hosted by University of Turin (https://eubi-xnat.hpc4ai.unito.it): 
### 1. SNR_SI_Brisque_ScanLevel and SNR_SI_Brisque_SubjectLevel:
Folders contain the codes to build containers to check the image quality at the scan level and subject level in XNAT platform, respectively, by calculating: 
- Signal to Noise Ratio (SNR) 
- Sharpness Index (SI) which refers to an image’s overall clarity and detail with higher values indicating sharper images.
- Blind/Referenceless Image Spatial Quality Evaluator (BRISQUE) a no-reference image quality score, uses Natural Scene Statistics (NSS) (It is concerned with the statistical regularities related to scenes) based model in spatial domain to perform quality estimation and distortion identification. The quality range is between 0 and infinite.
### 2. Mutual_Info_ScanLevel and Mutual_Info_SubjectLevel: 
Folders contain the codes to build the Mutual Information (MI) index container at the scan level and subject level in XNAT platform, respectively, which calculate the mutual dependency in the images with higher index corresponding to higher similarity between two consecutive acquisitions.This tool is more dedicated to the sequential acquisition data such as the DCE images.
