# ResUNet for tumor prediction and detection

This dataset contains brain MR images together with manual FLAIR abnormality segmentation masks.
The images were obtained from The Cancer Imaging Archive (TCIA).
They correspond to 110 patients included in The Cancer Genome Atlas (TCGA) lower-grade glioma collection with at least fluid-attenuated inversion recovery (FLAIR) sequence and genomic cluster data available.
Tumor genomic clusters and patient data is provided in `data.csv` file.


All images are provided in `.tif` format with 3 channels per image.
For 101 cases, 3 sequences are available, i.e. pre-contrast, FLAIR, post-contrast (in this order of channels).
For 9 cases, post-contrast sequence is missing and for 6 cases, pre-contrast sequence is missing.
Missing sequences are replaced with FLAIR sequence to make all images 3-channel.
Masks are binary, 1-channel images.
They segment FLAIR abnormality present in the FLAIR sequence (available for all cases).


The dataset is organized into 110 folders named after case ID that contains information about source institution.
Each folder contains MR images with the following naming convention:

`TCGA_<institution-code>_<patient-id>_<slice-number>.tif`

Corresponding masks have a `_mask` suffix.

Focal Tversky loss function with improved Attention U-Net for lesion segmentation has been used for pixel level classification.

State of the art results have been obtained by the use of the transfer learning

Download datasets for this project [here](https://drive.google.com/file/d/1-BmD81m2VNrVivqHsj5J--eXcmeP1nPm/view?usp=sharing) and [here](https://drive.google.com/file/d/1renmO-nK6BUFbWIFqFvEmoICxOTcE-X9/view?usp=sharing)

The project uses a custom library that needs to be placed in the same working directory of the .ipynb file, it can be found [here](https://drive.google.com/file/d/1OnKpwgV5Dmp4EwaUSEgAP6cGBZADT4yc/view?usp=sharing)
