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
•	A CSV file containing timestamp/age information, labels, and measurements in columns under variable names 'SubjectID', 'Label', 'Age', and 'Features'. Missing labels and missing values need to be assigned as empty cell and NaN, respectively.
<br />
•	Proportion of validation and test subjects to all available subjects in data partitioning.
<br />
•	Network parameters including the number of layer nodes, type of RNN, and activation functions.
<br />
•	Optimization parameters including the optimizer, RNN time step, and regularization and update rules.
<br />
•	Evaluation metric for validation and test predictions.
<br />

# Outputs
•	Training performance displayed on a progressive plot.
<br />
•	Validation performance displayed on a progressive plot.
<br />
•	Testing performance printed to the command window.
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
