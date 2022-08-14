# Open-World-Contrastive-Learning

This repo is used to show the implementation of the paper Open-World Contrastive Learning: https://arxiv.org/abs/2208.02764. 
Yiyou Sun, Yixuan Li

### Universe of Open-World Setting:
1. Images with labeled classes
1. Images without labels
    1. Images of known classes
    1. Images of novel unknown classes

Supervised learning is utilized often for cases with labeled samples. However, it becomes more difficult when there is a population of images that aren't labeled.

For the unlabeled image set:
1. Identify the set of images belonging to a novel class
1. For each image in the novel set, identify a positive and negative set of images
1. Utilize contrastive loss function to generate embeddings that have similar novel classes close together and dissimilar novel classes further apart
    1. We don't know the labels of these samples, but we would still like their embeddings to be similar/dissimilar from each other based on their unknown ground truth labels






The paper describes how OpenCon is helpful in representation learning in a open-world setting where there are labeled data points and unlabeled data points. The unlabeled samples can come from known or novel classes. That is we might have a set of newly generated images of cats that haven't been labeled, although our CIFAR data has cats as a known label. On the other hand, we might get newly generated images of footballs that is a new novel class not included in our known universe of CIFAR classes. The goal of OpenCon is to learn distinguishable representations of known and novel classes such that similar objects are grouped together.

The papers mentions 2 main challenges with this open-world setup that OpenCon addresses 1. the seperation of known vs novel class representations in the unlabeled dataset and 2. lack of supervision of novel classes. The authors introduce a prototype learning strategy to help learn distinguishable and compact representations for the unlabeled samples. The authors compare the prototype vectors of the unlabeled data to the prototype vectors of the known classes to identify potentially novel classes. These prototype vectors are updated as part of the training task. Lambda is a hyperparameter used to distinguish likely novel classes from known classes.

