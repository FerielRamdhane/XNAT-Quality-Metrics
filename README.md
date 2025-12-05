# Quality Metric Tool - XNAT User Guide
## Tool Overview
This repository is sharing docker images developped at the Euro-BioImaging MED-Hub  and National Research Council (CNR) for the XNAT platform hosted by University of Turin. (https://eubi-xnat.hpc4ai.unito.it): A suite of four Image Quality Assessment (IQA) metrics designed to evaluate the perceptual quality of preclinical and medical image datasets within the XNAT platform. It **can also be run locally** for testing or development.  
It supports **scan-level** and **subject-level** analysis using the following metrics:

- Signal to Noise Ratio (SNR) is used to characterise image quality with higher values indicating better image quality
- Sharpness Index (SI) which refers to an image’s overall clarity and detail with higher values indicating sharper images.
- Mutual Information (MI) index calculates the mutual dependency in the images with higher index corresponding to higher similarity between two consecutive acquisitions.This tool is more dedicated to the sequential acquisition data such as the DCE images.
- Rician Noise Level estimation: is based on the Mean Absolute Deviation to estimate the Rician noise in MRI.

## User Manual

### Steps to Deploy on XNAT Instance

1. Pull the appropriate Docker image:
```bash
# For scan-level analysis
docker pull iqaxnat_scan:latest

# For subject-level analysis
docker pull iqaxnat_subject:latest

---
Licence

