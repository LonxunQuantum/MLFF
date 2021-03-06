# Machine Learning Force Field

## Introduction:

Machine Learning Force Field (MLFF) is an open source software under GNU GPL license. It aims at generating force fields with accuracy comparable to Ab Initio Molecular Dynamics (AIMD). It is compatible with AIMD data in either **PWmat** or **VASP** format. 

**Manual**

A complete user manual can be found here: http://doc.lonxun.com/MLFF/MLFF.html

**Data Archive**

We provide an archive of AIMD data obtained from various systems, some of which are extremely challenging for machine learning force field. You may use them for benckmarking, as well as for developing new features and training models. You can access the archive via https://www.jianguoyun.com/p/DUWoiP4Ql-_OChiEk8IEIAA  

This package contains 8 types of features with translation, rotation, and permutation invariance, which are

        1. 2-body(2b)
        2. 3-body(3b) 
        3. 2-body Gaussian(2bgauss)
        4. 3-body Cosine(3bcos) 
        5. Multiple Tensor Potential(MTP)
        6. Spectral Neighbor Analysis Potential(SNAP)
        7. DP-Chebyshev(dp1)        
        8. DP-Gaussian(dp2) 

and 4 engines for training and prediction, which are 

        1. Linear Model
        2. Nonlinear VV Model
        3. Kalman Filter-based Neural Netowrk (KFNN)
        4. Kalman Filter-based DP-torch Model(KFDP)

In practice, user may freely combining features with models (except for Deep Potential model, since it defines feature differerntly). A illustration of such a process is shown below. In future, we will also add support for user-defined features and training model. 

An complete MLFF workflow contains 3 major steps. **Firstly**, use eitehr PWmat or VASP to run AIMD calculation to generate training data (features and direvatives of features, .etc), and perform post-processing of the data. **Secondly**, run training engine to obtain the force field; **Finally**, use the obtained force field to make inference, which includes **test** and **prediction**. 
