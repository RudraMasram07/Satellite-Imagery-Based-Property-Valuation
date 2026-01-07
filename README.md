# Satellite-Imagery-Based-Property-Valuation
A multimodal machine learning project that predicts house prices by combining tabular housing data with satellite image features extracted using deep learning.

The file contains clearly separated sections for:

Satellite Image Downloading and Local Storage:
Satellite images are fetched using latitude and longitude coordinates through a custom data-fetching routine based on ArcGIS World Imagery. Images are downloaded once and stored locally on disk to avoid repeated fetching, improve efficiency, and ensure reproducibility.

Exploratory Data Analysis (EDA):
This section analyzes the distribution of house prices, spatial price patterns, and sample satellite images to understand trends, outliers, and relationships that guide modeling decisions.

Tabular Baseline Models:
Multiple regression models are trained using only structured housing attributes to establish baseline performance. These models serve as reference points for evaluating the impact of adding satellite image features.

CNN-Based Image Feature Extraction (ResNet-18):
Locally stored satellite images are processed using a pretrained ResNet-18 convolutional neural network. The model is used as a feature extractor to generate fixed-length embeddings that capture neighborhood-level visual characteristics.

Multimodal Feature Fusion and XGBoost Regression:
The CNN-derived image embeddings are combined with tabular features through feature concatenation. The fused features are then used to train an XGBoost regression model for predicting house prices.

Grad-CAM Explainability:
Grad-CAM is applied to visualize which regions of satellite images influence the CNN’s learned representations, improving interpretability and validating that the model focuses on meaningful spatial features.

Final Price Prediction:
The trained regression model is used to generate house price predictions for the test dataset, and the results are saved as a CSV file for final evaluation or submission.
