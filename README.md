# Persian Handwritten Math Expression Recognition

This repository contains the implementation of a complete machine learning pipeline for recognizing mathematical expressions from Persian handwritten images. This project was developed as the final project of the Machine Learning course,  instructed by Dr. Mostafa Tavassolipour and Dr. Mohammadreza Abolghasemi, at the School of Electrical and Computer Engineering, University of Tehran in Spring 2025. 

## Project Overview

The primary objective of this project is to tackle a significant real-world challenge: the scarcity of labeled data for training artificial intelligence models. In this system, input images containing mathematical expressions are processed using neural networks and Semi-supervised Learning techniques to localize each character and ultimately classify them.  

## Main Phases

The system is designed and implemented in three core phases:

### 1. Character Localization

In the first phase, Region-based Convolutional Neural Networks (R-CNN) are utilized to detect the exact location and dimensions of each character within the image. Adhering to the project's academic standards, the network architecture is implemented entirely from scratch without the use of pretrained weights. The evaluation metrics for this phase include Intersection over Union (IoU), Precision, and Recall.  

### 2. Feature Extraction & Clustering

During this stage, character images are cropped based on their bounding boxes, and traditional methods are applied to extract their features. Subsequently, various clustering algorithms are employed to group the characters, accompanied by visualizations of cluster centers and outliers.  

### 3. Mathematical Expression Recognition

Given that exact mathematical expression labels were available for only a small subset of the training data, this phase is formulated as a semi-supervised learning problem. The final model predictions are evaluated using the Levenshtein distance between the predicted expression and the ground truth.  

## Dataset

The dataset utilized in this project was entirely generated and collected by the students of the class. The data distribution is as follows:

- **Train:** Contains 300 images. While bounding boxes are provided for all characters in these images, the exact mathematical expression labels are only available for 8 images, making it a highly incomplete dataset designed for semi-supervised learning.
- **Validation:** Contains 200 images. Complete labels, including both bounding boxes and full mathematical expressions, are available for all images in this set.  
- **Test:** Contains 200 images. These images are provided without any labels and are strictly used for final performance benchmarking.  

All labels are provided in `json` format, with bounding box attributes defined as `x, y, width, height` in pixels.  

## Usage & Structure

### Quick Start

To get started with this project, clone the repository to your local machine:

```bash
git clone https://github.com/feta-feta/Handwritten-Math-Recognition.git
cd Handwritten-Math-Recognition
```

### Structure

All main project scripts are located in the `src` directory, and dependencies required to set up the environment are listed in `requirements.txt`. The outputs, including model execution results, generated images, and evaluations, are saved in the `results` directory. The final visual evaluations are accessible through the notebook.

## Results & Visualizations

The complete visual results, model evaluations, and clustering plots are fully documented and can be viewed in the `visualizations.ipynb` notebook. 



![image-20260528211236803](C:\Users\fatem\AppData\Roaming\Typora\typora-user-images\image-20260528211236803.png)



## References

The character localization module in this project builds upon the foundational concepts and architecture introduced in the following research paper:

* Shaoqing Ren, Kaiming He, Ross Girshick, and Jian Sun. (2015). **Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks**. *Advances in Neural Information Processing Systems (NeurIPS)*. [arXiv:1506.01497](https://arxiv.org/abs/1506.01497)