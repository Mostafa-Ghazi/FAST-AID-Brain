# FAST-AID Brain
Fast and Accurate Segmentation Tool using Artificial Intelligence Developed for Brain
<br />

# Description
The FAST-AID Brain can be applied to T1-weighted brain MRI scans to segment the human brain into  132 regions robustly and accurately, without any preprocessing or postprocessing steps, and used for the estimation of the intracranial volume based on the obtained annotations. This toolbox is an implementation of the algorithm proposed in [1].
<br />

# Algorithm
The model uses an efficient U-Net-like network and benefits from the intersection points of different views and hierarchical relations for the fusion of the orthogonal 2D planes and brain labels during the end-to-end training. Weakly supervised learning is deployed to take the advantage of partially labeled data, and MRI-based data augmentation [2] is used to expand the data by generating realistic brain scans with high variability for robust training of the model while preserving data privacy.
<br />

# Dependencies
Singularity (tested with v3.0.0).
<br />

# Inputs
•	T1-weighted brain MRI scans of any desired file names and supported extensions (nii, nii.gz, img/hdr, mgh, mgz, dcm) can be placed in one desired input directory as
<br />
/input-dir/
<br />
&emsp;&emsp;&emsp; MRI1.nii
<br />
&emsp;&emsp;&emsp; MRI2.nii.gz
<br />
&emsp;&emsp;&emsp; MRI3.img, MRI3.hdr
<br />
&emsp;&emsp;&emsp; MRI4.mgh
<br />
&emsp;&emsp;&emsp; MRI5.mgz
<br />
&emsp;&emsp;&emsp; MRI6/ seq1.dcm, seq2.dcm, …, seqN.dcm
<br />

# Outputs
•	The scaled brain MRI scans and segmentations will be saved in the desired output directory with the same input file names followed by the resolution and a segmentation tag as
<br />
/output-dir/
<br />
&emsp;&emsp;&emsp; MRI1_1mm.nii.gz, MRI1_1mm_seg.nii.gz, MRI1_seg.nii.gz
<br />
&emsp;&emsp;&emsp; MRI2_1mm.nii.gz, MRI2_1mm_seg.nii.gz, MRI2_seg.nii.gz
<br />
&emsp;&emsp;&emsp; MRI3_1mm.nii.gz, MRI3_1mm_seg.nii.gz, MRI3_seg.nii.gz
<br />
&emsp;&emsp;&emsp; MRI4_1mm.nii.gz, MRI4_1mm_seg.nii.gz, MRI4_seg.nii.gz
<br />
&emsp;&emsp;&emsp; MRI5_1mm.nii.gz, MRI5_1mm_seg.nii.gz, MRI5_seg.nii.gz
<br />

# Usage
•	A simple command for running the program is
<br />
&emsp; `singularity run --nv fast_aid_brain.sif /input-dir/ /output-dir/ 16 gpu weighted-majority uint8 1 2`
<br />
where 16 is the minibatch or patch size and can be adjusted based on the NVIDIA GPU memory size, gpu is the execution environment, weighted-majority indicates the algorithm used for the fusion of the three orthogonal planes, uint8 assigns the output file type, 1 is used for postprocessing, and 2 is set to generate isotropic 1 mm brain scan and its segmentations as well as the annotations for the image of the same resolution.
<br />

# Citation
When you publish your research using this toolbox, please cite [1] as
<br />
<br />
@article{Ghazi2022,
<br />
  title = {{FAST-AID Brain}: Fast and Accurate Segmentation Tool using Artificial Intelligence Developed for Brain},
  <br />
  author = {Mehdipour Ghazi, Mostafa and Nielsen, Mads},
  <br />
  journal = {},
  <br />
  year = {2022},
  <br />
  pages={},}
<br />

# References
[1] Mehdipour Ghazi, M., Nielsen, M., 2022. FAST-AID Brain: Fast and Accurate Segmentation Tool using Artificial Intelligence Developed for Brain. arXiv preprint arXiv:XXXX.YYYY, 2022.
<br />
[2] Mehdipour Ghazi, M., 2022. MRI-Augmentation: A toolbox for MRI-based data augmentation.
<br />

Contact: mostafa.mehdipour@gmail.com
<br />
