## What is this repository for?
This repository is sharing docker images developped at the Euro-BioImaging MED-Hub  and National Research Council (CNR) for the XNAT platform hosted by University of Turin. (https://eubi-xnat.hpc4ai.unito.it): A suite of four Image Quality Assessment (IQA) metrics designed to evaluate the perceptual quality of clinical image datasets within the XNAT platform at the scan and subject levels. The tool outputs Excel files containing the mean and median for each metric and scan, as well as PNG files with corresponding histogram plots.
### 1. quality_metrics/snr_si_metrics and quality_metrics/snr_si_metrics_subj 
Docker images to check the quality of DICOM images at the scan and Subject level on XNAT platform,respectively, by calculating: 
- Signal to Noise Ratio (SNR) 
- Sharpness Index (SI) which refers to an image’s overall clarity and detail with higher values indicating sharper images.

### 2. quality_metrics/mutual_information_metric and quality_metrics/mutual_information_metric_subj 
Docker images to check the Mutual Information (MI) index container at the scan level and subject level in XNAT platform, respectively, it calculate the mutual dependency in the images with higher index corresponding to higher similarity between two consecutive acquisitions.This tool is more dedicated to the sequential acquisition data such as the DCE images.
