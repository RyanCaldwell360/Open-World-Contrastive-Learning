# Open-World-Contrastive-Learning

This repo is used to show the implementation of the paper Open-World Contrastive Learning: https://arxiv.org/abs/2208.02764. 
Yiyou Sun, Yixuan Li

The paper describes how OpenCon is helpful in representation learning in a open-world setting where there are labeled data points and unlabeled data points. The unlabeled samples can come from known or novel classes. The goal of OpenCon is to learn distinguishable representations of known and novel classes such that similar objects are grouped together.

The papers mentions 2 main challenges with this open-world setup that OpenCon addresses 1. the seperation of known vs novel class representations in the unlabeled dataset and 2. lack of supervision of novel classes. The authors introduce a prototype learning strategy to help learn distinguishable and compact representations for the unlabeled samples.

### Universe of Open-World Setting:
1. Images with labeled classes
1. Images without labels
    1. Images of known classes
    1. Images of novel unknown classes

### Methodology
1. Pretrained Image Encoder (ResNet50)
    1. Pretraining done based on this paper/code: https://arxiv.org/abs/2002.05709?context=stat.ML and https://github.com/google-research/simclr
1. Data Prep
    1. Select mini-batch of labeled and unlabeled data
    1. Augment data twice
    1. Generate normalized embeddings of augmented data
1. Identify Novel Images
    1. Calculate novelty threshold (lambda)
    1. Seperate novel images from unlabeled set of images
1. Select Positive/Negative Images
    1. For novel set, assign psuedo-labels based on prototype prediction
    1. Obtain P and N from augmented mini-batches
1. Update Model Weights
    1. Calculate contrastive loss on mini-batches
    1. Update weights of the encoder using backprop
1. Update Prototype Vectors
    1. Use equation 6 in paper





