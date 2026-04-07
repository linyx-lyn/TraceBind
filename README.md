# TraceBIND

- [Overview](#overview)
- [Installation](#installation)
- [Tutorials](#tutorials)
- [Citation](#citation)
  
[![DOI](https://zenodo.org/badge/993986521.svg)](https://doi.org/10.5281/zenodo.19446219)

<img src="https://github.com/lyx-lin/TraceBIND/blob/main/figures/tracebind_overview.png">

## Overview
The identification of footprints provides a powerful means to detect base-pair resolution signals of regulatory elements in chromatin accessibility data. We observe substantial variability in Tn5 transposase cleavage bias across individual samples, highlighting the need for sample-specific correction. TraceBIND is a R package that that corrects sample-specific Tn5 bias through mitochondria-based fine-tuning of PRINT’s deep learning model, and use it to identify TF and nucleosome footprints through a dynamic flanking window statistical scan. TraceBIND also enables sample-specific FDR-controlled p-value thresholds stratified by varying coverage, which is necessary because coverage can vary across orders of magnitude in ATAC-seq data.

## Installation
Before installing this package, make sure you have the following dependencies installed:
```bash
# install.packages("devtools")
devtools::install_github("yaowuliu/ACAT")
```

TraceBIND has been tested on python=3.11, 3.12. The requirements of python packages for traceBIND finetuning are listed in the [requirements](https://github.com/lyx-lin/TraceBIND/blob/main/requirements.txt), which can be done by:
```bash
pip install -r requirements.txt
```

Then install this package:
```bash
# install.packages("devtools")
devtools::install_github("lyx-lin/TraceBIND", dependencies=TRUE)
```

## Tutorials 
Please refer to the following jupyter notebooks for tutorials:
 * [Finetuning sample-specific Tn5 bias model on mito DNA](https://github.com/lyx-lin/TraceBIND/blob/main/tutorials/tutorial_finetuning.ipynb)
(Before finetuning, please download [PRINT Tn5 bias model](https://github.com/HYsxe/PRINT/blob/main/data/shared/Tn5_NN_model.h5))
 * [Identification of footprints](https://github.com/lyx-lin/TraceBIND/blob/main/tutorials/tutorial_footprint_identification.ipynb)
 * [Footprint-informed chromVar analysis](https://github.com/lyx-lin/TraceBIND/blob/main/tutorials/tutorial_chromvar.ipynb)

The data used could be found [here](https://www.dropbox.com/scl/fo/zhmxfp0gxnmlgeo8jsmbv/AO3I75Lz6eP3Illn-eb0Zgc?rlkey=zkfi6c7c29eb11tbmcz80n8sf&st=2cstifvu&dl=0).

## Citation
For more model details, validation results and real dataset analysis, please check out our manuscript on bioRXiv. If you use our method, please use the following citation:
```
@article {Lin2025.10.17.683160,
	author = {Lin, Yuxuan and Wang, Hanzhi and Wilson, Parker C. and Zhang, Nancy R.},
	title = {Robust footprinting with sample-specific Tn5 bias correction for bulk and single cell ATAC-seq},
	elocation-id = {2025.10.17.683160},
	year = {2025},
	doi = {10.1101/2025.10.17.683160},
	publisher = {Cold Spring Harbor Laboratory},
	URL = {https://www.biorxiv.org/content/early/2025/10/18/2025.10.17.683160},
	journal = {bioRxiv}
}
```
