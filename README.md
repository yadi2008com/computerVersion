# computerVision
#Scene Recognition  
#Data 
The training data consists of 100 images for each of the 15 scene classes. These are arranged in directories named according to the class name. The test data consists of 2985 images. All the images are provided in JPEG format. All the images are grey-scale, so you don't need to consider colour.

#Objective measure  
The key classification performance indicator for this task is average precision;  

#Run conditions  
Run #1: a simple k-nearest-neighbour classifier using the "tiny image" feature. The "tiny image" feature is one of the simplest possible image representations. One simply crops each image to a square about the centre, and then resizes it to a small, fixed resolution (we recommend 16x16). The pixel values can be packed into a vector by concatenating each image row. It tends to work slightly better if the tiny image is made to have zero mean and unit length. You can choose the optimal k-value for the classifier.  

Run #2:  a set of linear classifiers (an ensemble of 15 one-vs-all classifiers) using a bag-of-visual-words feature based on fixed size densely-sampled pixel patches. We recommend that you start with 8x8 patches, sampled every 4 pixels in the x and y directions. A sample of these should be clustered using K-Means to learn a vocabulary (try ~500 clusters to start). You might want to consider mean-centring and normalising each patch before clustering/quantisation. Note: we're not asking you to use SIFT features here - just take the pixels from the patches and flatten them into a vector &amp; then use vector quantisation to map each patch to a visual word.  

Run #3: the best classifiers you can! You can choose whatever feature, encoding and classifier you like. Potential features: the GIST feature; Dense SIFT; Dense SIFT in a Gaussian Pyramid; Dense SIFT with spatial pooling (commonly known as PHOW - Pyramid Histogram of Words), etc. Potential classifiers: Naive bayes; non-linear SVM (perhaps using a linear classifier with a Homogeneous Kernel Map), ... 
