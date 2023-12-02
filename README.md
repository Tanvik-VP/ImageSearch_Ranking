# ImageSearch_Ranking
This repository hosts the code and documentation for a semantic image search service. Developed based on deep learning techniques, this project enables efficient and accurate image retrieval by leveraging similarity search models.
The task is to generate a ranked list of images which are semantically similar to the query image


### Key Features:

Uses a dataset of 1000 images across 20 categories from caltech 101.
Employs a pre-trained VGG16 model on Imagenet for generating image embeddings.
Implements various search methods, including traditional image similarity and semi-supervised approaches for more targeted results.
Demonstrates the use of embeddings to enhance search efficiency and accuracy.

## Getting Started

Data: (https://drive.google.com/drive/folders/1kLMG1pa3xV_TwK0DnibSbjYrj_hjGttf?usp=share_link)
add this data into `data/ folder in your project

- 1. Install all the packages which is provided in Requirements.txt
  2. Run the `Visualization.ipynb to understand the data which is in notebooks folder
  3. Run the `generate_embeddings.py to generate the embeddings
  4. check out `EmbeddingVisualization.ipynb to understand how embeddings have stacked based on labels - PCA
  5. Run `ModelEvaluation.ipynb to evaluate 2 models
 
#### Metrics
We use We use the Precision @ K metric to measure the performance of the system.
Precision@K = number of relevant items in top K / K
As this metric does not focus on the rank of the entries and only focuses on the number of relevant entries. To capture the ranking factor of the system, we also present Average Precision(AP) on the dataset.


For this exercise, I present two baselines.

Baseline 1: In this method, I randomly take 10 samples from the candidate set across all classes and do this for each query and calculate the metric.

Baseline 2: In this method, I use the embeddings generated from MobileNetV2 model and use cosine distance as similarity metric to rank candidate entries.

References:
[1] Caltech 101, (http://www.vision.caltech.edu/Image_Datasets/Caltech101/) 
[2] Mean Average Precision (MAP) For Recommender Systems, (https://sdsawtelle.github.io/blog/output/mean-average-precision-MAP-for-recommender-systems.html)
