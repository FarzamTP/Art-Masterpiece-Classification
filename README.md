# Art Masterpieces Classification
## Abstract
Working with big data sets like [art masterpieces](https://www.kaggle.com/ikarus777/best-artworks-of-all-time), that data are stored in specific directories make it a little hard. But for each class (Artist) there wasn’t balanced number of images. So I came with the idea of image generation to generate more images for training and also testing. The idea can be implemented with Tensorflow Image Generator library.

## Solution
For training I started to use a subset of training so I choose 10 classes and split them into train and test set and stored them temporary directories. The image data generator pointed to each train and test directory separately and generated random images with given arguments. Then I built a Sequential model and fit them the train and test data generators.<br> 
After 7 hours of training on [Google Colab](https://colab.research.google.com/drive/16o9G38afHWMiXDNGjs22w5echN5xbYCe), It reached accuracy of 83% over training set and 62% over test set.

## Evaluation
For such a big data set, I managed to use different size of subsets and I saw that the greater the data set gets, the more images ImageGenerator generates. As shown below with 10 classes of paintings, the loss value and accuracy changed over time:
<br>
![Train and validation accuracy plot](https://github.com/FarzamTP/Art-Masterpiece-Classification/blob/master/plots/acc/15_classes_100_epochs_0.8512_0.6205.png)
<br>
![Train and validation loss plot](https://github.com/FarzamTP/Art-Masterpiece-Classification/blob/master/plots/loss/15_classes_100_epochs_0.4186_1.4773.png)

## Conclusion
After training the model and evaluating over test set I tried lowering and increasing learning rate and also using RMSProp and Adam optimizer, but the result with given hyper parameters reached the best score and also performed in shorter time.
