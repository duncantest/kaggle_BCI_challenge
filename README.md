# INRIA BCI Challenge
This repository contains the code I used for the winning solution for the INRIA BCI challenge hosted on Kaggle.

https://www.kaggle.com/c/inria-bci-challenge

# Hardware and OS
* 8 Intel Celeron M processors (1.5GHz), 64 GB RAM, 512 GB SSD 
* Ubuntu 14.04.2

# Software and version numbers
* Python - 2.7.6
  * scikit_learn - 0.14.1
  * numpy - 1.8.2
  * pandas - 0.13.1
* Matlab - R2014b (see www.mathworks.com)
  * JSONlab (this can be downloaded from http://www.mathworks.com/matlabcentral/fileexchange/33381-jsonlab--a-toolbox-to-encode-decode-json-files-in-matlab-octave)

n.b. it may be possible to use Octave (free) instead of Matlab (proprietary) but I haven't tested my code using Octave. 

# Settings.json
# Generating features
There are five Matlab scripts (generate_meta_features.m, get_sess5_retrial_features.m, get_ave_amplitude_features.m, get_template_features1.m and get_template_features1.m) which will generate the features used in my model. It's important to run these scripts in order as latter scripts use data produced by the former scripts. First run  generate_meta_features.m, then get_sess5_retrial_features.m, next get_ave_amplitude_features.m, then get_template_features1.m and finally get_template_features1.m.

To run generate_meta_features.m, simply type in the following from within matlab 

`generate_meta_features`

or from within a terminal

`matlab -r "generate_meta_features"`

You will see the following printed to screen

`Obtaining meta features for training set .....`
`Training set subject 2, session 1`
`Training set subject 2, session 2`

After the script is complete run get_sess5_retrial_features.m, get_ave_amplitude_features.m, get_template_features1.m and finally get_template_features1.m.

On my machine generate_meta_features.m takes ~5 mins to run, get_sess5_retrial_features.m ~1 min,  get_ave_amplitude_features.m a few days, get_template_features1.m a few days and get_template_features1.m ~1 day. There is a lot of scope to parallelise the code in get_ave_amplitude_features.m, get_template_features1.m and get_template_features1.m to speed things up.

For convenice I've placed the feature files generated by these scripts in the feature_files folder within this repository, so there is no need to generate them from scratch.

# Fitting the model
# Predicting using the model
# Description of features
