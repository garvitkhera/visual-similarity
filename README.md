# flixstock
Finding Visually Similar Garments for an Input Garment

This repository contains a jupyter notebook in which a task of finding visually similar garments from a given input image is performed. 
Framework used: Pytorch

# Steps:
1: I've used resnet50 architecture to extract features from the images database. I've removed the last avgpool and fully connected layer to extract a feature vector of size (2048,7,7).

2: For passing the images in resnet50 model, first we need to perform some preprocessing. 
    i: Reshaping the input to (224 * 224).
    ii: Normalizing the input
    iii: Converting to a 4D tensor as pytorch model expects a 4D tensor.
  
3: Saving the feature vectors of all images to a dictionary with the image name as keys and it's feature vector as values.

4. Now for finding 10 visually similar garments, I used 'Cosine Similarity' and comparing the input feature vector to all the image's features.

5. An output is received with all the similarity values with the input image and taking the top 10 similarities and plotting those results and saving them too in the Suggestions folder.
