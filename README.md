# Paper_Metabolomics_CWGAN-GP
Reproducible science code for the paper 'Enhancing Supervised Analysis of Imbalanced Untargeted Metabolomics Datasets Using a CWGAN-GP Framework for Data Augmentation' about the use of CWGAN-GP framework for untargeted mass spectrometry metabolomics data augmentation.

Here for each of the 6 datasets analysed, we have 2 different Jupyter notebooks, one regarding the comparison of CWGAN-GP GAN generated data to experimental data with the termination '- Characteristics' and one regarding the effect of minority class data augmentation in imbalanced datasets on the performance of supervised statistical models with the termination '- Imbalanced'. One dataset (GD) only has one corresponding notebook ('- Characteristics'), since it was considered to small to perform the class imbalance study.

In these notebooks, there is a `GENERATE=True` when training the GAN to train it for the first time. After one time, it is store in the folder `gan_models`, and `GENERATE` can be set to `False`. The same is true for some instances where linear augmentation is made and stored in `store_data` (instances where it takes a long time to run this augmentation).

Furthermore, there is a 12th and 13th notebooks (`DataAug - CWGAN-GP - Synthetic Dataset Testing.ipynb` and `DataAug - CWGAN-GP - Synthetic Dataset Testing - Sensitivity Analysis.ipynb`) for the analysis of synthetic made datasets and the impact of class separation on the improvement of the performance of supervised statistical models when minority class data augmentation is made.

The 6 datasets analysed are presented in their respective notebooks and a reference to their original paper of publication and the repository where the dataset is available are shown near the begginning of each respective notebook.

The .py files contain supporting functions for the jupyter notebooks:
- `multianalysis.py` - functions for multivariate statistical analysis.
- `GAN_functions.py` - functions for building and training CWGAN-GPs.
- `linear_augmentation_functions.py` - functions for linear augmentation.
- `gan_evaluation_metrics.py` - functions for comparing GAN and Experimental data.
- `elips.py` - functions to draw confidence ellipses in PCA projection plots.

The `store_data` and `gan_models` folder are present to store linear augmented datasets (when they are stored) and trained CWGAN-GP Generator and Critic models, while images `folder` is present to save figures made in the notebooks.

The remaining .xlsx, .csv, .txt, .json or .h5 files correspond to the data from the 6 different datasets analysed which are read after in their respective notebooks.

Some of the optimizations made for the CWGAN-GP models are present in the repository with the available code from project CPCA/A0/467905/2021: https://github.com/fticr-sms/Metabolomics_DataAug_Optimization (currently being made).

We thank the online platforms such as Tensorflow (as an example https://www.tensorflow.org/tutorials/generative/dcgan), Keras (as an example https://keras.io/examples/generative/wgan_gp/#wasserstein-gan-wgan-with-gradient-penalty-gp) and machinelearningmastery among others for their tutorials on the architecture and training of different types of GANs.
