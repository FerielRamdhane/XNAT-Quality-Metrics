# Quality Metric Tool - XNAT User Guide
## Tool Overview
This repository is sharing docker images developped at the Euro-BioImaging MED-Hub  and National Research Council (CNR) for the XNAT platform hosted by University of Turin. (https://eubi-xnat.hpc4ai.unito.it): A suite of four Image Quality Assessment (IQA) metrics designed to evaluate the perceptual quality of preclinical and medical image datasets within the XNAT platform. It **can also be run locally** for testing or development.  
It supports **scan-level** and **subject-level** analysis using the following metrics:

- Signal to Noise Ratio (SNR) is used to characterise image quality with higher values indicating better image quality
- Sharpness Index (SI) which refers to an image’s overall clarity and detail with higher values indicating sharper images.
- Mutual Information (MI) index calculates the mutual dependency in the images with higher index corresponding to higher similarity between two consecutive acquisitions.This tool is more dedicated to the sequential acquisition data such as the DCE images.
- Rician Noise Level estimation: is based on the Mean Absolute Deviation to estimate the Rician noise in MRI.
  
| Metric Name       | Description |
|------------------|-------------|
| snrsi             | **Signal-to-Noise Ratio**: characterizes image quality (higher = better)<br>**Sharpness Index (SI)**: measures clarity/detail (higher = sharper) |
| mi                | **Mutual Information (MI)**: measures dependency between images (higher = more similar)<br>Dedicated for sequential acquisition data such as DCE images |
| riciannoiselevel  | **Rician Noise Level**: estimation based on the Mean Absolute Deviation to measure Rician noise in MRI |

Output: The tool generates both Excel files and PNG histogram plots for each metric:
1. Excel Files (.xlsx): Contains the mean, median and stds for each metric and scan/subject.
2. PNG Files (.png) Histogram plots corresponding to each metric.

## User Manual

### Using the Docker image

To build and run the container from the root of this repository
1. Pull the appropriate Docker image:
```bash
# For scan-level analysis
docker pull iqaxnat_scan:latest

# For subject-level analysis
docker pull iqaxnat_subject:latest

```
2. Verify the Docker image:
```
docker images
```
3. Running Locally
* Ensure Docker is installed on your local machine.
* Pull the appropriate Docker image as above.
* Prepare input and output directories on your local system.
* Command Format
  ```
  docker run -v path_of_input:/input -v path_of_output:/output [IMAGE_NAME] [METRIC_NAME]
  ```
| Parameter      | Description                                                      |
| -------------- | ---------------------------------------------------------------- |
| path_of_input  | Directory containing scan/subject data |
| path_of_output | Directory to store analysis results                              |
| IMAGE_NAME     | Docker image (`iqaxnat_scan:latest` or `iqaxnat_subject:latest`) |
| METRIC_NAME    | IQA metric(s), space-separated for multiple metrics              |

4. Examples
- Scan-Level Analysis
 ```
docker run -v /data/xnat/scans:/input -v /data/xnat/results:/output iqaxnat_scan:latest snrsi
```
- Multiple Metrics
```
docker run -v /data/xnat/scans:/input -v /data/xnat/results:/output iqaxnat_scan:latest snrsi mi riciannoiselevel
 ```

