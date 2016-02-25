# homogenPy
Python pipeline for homogeneity analysis of MSI datasets


homogenPy is a python pipeline to perform homogeneity assessment of MSI dataset(s). 
Our pipeline contains different functions to understand drug distribution by taking advantage from different texture analysis based methods, such as intensity histogram based, gray-level co-occurence matrix (GLCM) based, size-zone matrix (SZM) based and shape factor based. 

The pipeline relies mainly on numpy, scipy, skimage, argparse python modules. There are some specific dependencies as well, discussed below. Pipeline main methods are : 

1) GetIonImage : import and visualization of data from Analyze 7.5 format. This function offers ion intensity map at user defined mass range (.sim),  three different types of segmentation map :
	a) drug mask(default, _drug.msk, drug mask.jpg) b) tic image mask (_tic.msk, _ticmsk.jpg)  c) maximum intensity value mask(_mim.msk, _mimmsk.jpg)
 	 
2) GCLM_features : This function will return 13 Haralick texture features based on gray-level co-occurence matrix for input image. Before features calculation, tissue image will multiple with corresponding mask image to place tissue object on uniform background. Hence results were obtained from tissue object only.

3) SB_features : This function will calculate shape based features for tissue mask image. It will return: number of small disconnected objects within tissue, their area and perimeter. Required : cv2 python module.

4) SZM_features : This function will return 11features calculated on size-zone based matrix. Required : rpy2 python module and r-library radiomics

5) GLRLM_features : This function will return 11 features calculated on run-length matrix. 
