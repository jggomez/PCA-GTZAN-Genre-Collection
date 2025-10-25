# GTZAN Genre Collection PCA Analysis

This notebook performs a Principal Component Analysis (PCA) on the GTZAN Genre Collection dataset to explore the underlying structure of the audio data based on spectral features.

## Dataset

The dataset used is the GTZAN Genre Collection, which contains 1000 audio tracks (100 per genre).

## Process

1. **Installation of Libraries:** Necessary libraries, including `librosa`, `pandas`, `numpy`, and `rich`, were installed.
2.  **Data Download:** The GTZAN dataset was downloaded using `kagglehub`.
3.  **Data Loading and Feature Extraction:**
    *   A function `extract_spectral_features` was defined to load audio files, perform Short-Time Fourier Transform (STFT) to obtain the magnitude spectrogram, and calculate the mean spectrum vector by averaging the magnitude over time.
    *   This function was applied to all audio files in the dataset to create a data matrix `X` where each row represents an audio segment and each column represents a frequency band. The corresponding genre labels were also stored.
4.  **Data Standardization:** The feature matrix `X` was standardized using `StandardScaler` to ensure that each frequency band contributes equally to the PCA, regardless of its original scale.
5.  **PCA Calculation:** Principal Component Analysis was performed on the standardized data using `PCA` from `sklearn.decomposition`. The explained variance ratio, eigenvalues, and eigenvectors (loadings) were calculated.
6.  **Explained Variance Analysis:** The explained variance ratio of each principal component was analyzed, and a bar plot was generated to visualize the variance explained by the first 10 components and the cumulative explained variance.
7.  **Loadings Analysis:** The loadings (eigenvectors) were examined to understand the contribution of each frequency band to the principal components. Bar plots were generated to visualize the top frequency bands contributing to the first two principal components. A table showing the top frequency bands with the highest loadings for PC1 was also displayed.
8.  **Component Visualization:** Scatter plots were generated to visualize the data in the space of the first few principal components (PC1 vs PC2 and PC1 vs PC2 vs PC3), colored by musical genre, to observe potential clustering or separation of genres.

<img width="924" height="390" alt="image" src="https://github.com/user-attachments/assets/bc59c5b4-04a5-4160-892e-8ac5fdad6dd7" />

<img width="841" height="547" alt="image" src="https://github.com/user-attachments/assets/27723e5b-0a7c-4f59-8f53-ea8be3965cd5" />

<img width="1489" height="590" alt="image" src="https://github.com/user-attachments/assets/d1b1ecd7-9246-48e5-b845-770126518711" />

<img width="1001" height="790" alt="image" src="https://github.com/user-attachments/assets/d6f29926-2ec2-4fc5-9c94-2c69a0540a95" />

## Results

The PCA analysis revealed that the first few principal components capture a large proportion of the variance in the spectral features. The loadings provided insights into which frequency bands are most important for these components. The PCA visualization showed some degree of genre separation, suggesting that spectral features help distinguish among musical genres.

Further analysis could involve using PCA-transformed data for clustering or classification to evaluate the separability of the musical genres formally.

## Author

* **Juan Guillermo Gómez**
* Linkedin: [@jggomezt](https://www.linkedin.com/in/jggomezt/)
