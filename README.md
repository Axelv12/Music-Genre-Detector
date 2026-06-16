# Music Genre Detector

This project is a Machine Learning-based Music Genre Classifier built with R. It analyzes audio files, extracts acoustic and rhythmic features, and uses a Random Forest model to classify the songs into different genres.

## Features Extracted

The model uses various audio features to distinguish between genres, including:
- **Mel-frequency cepstral coefficients (MFCCs)**
- **Spectral Features**: Centroid, Bandwidth, RollOff, and Band Energy Ratio (BER).
- **Time-Domain Features**: Zero Crossing Rate (ZCR), Average Energy, and Standard Deviation of Energy.
- **Rhythmic Features**: Tempo (BPM), Pulse Strength, Onset Rate, High Onset Mean, and Offbeat Ratio.

## Technologies Used

- **R**: The core programming language used for analysis and modeling.
- **Python (Reticulate)**: Used to integrate `librosa` for advanced rhythmic and onset feature extraction.
- **Audio Processing Libraries**: `tuneR`, `seewave` (in R), and `librosa` (in Python).
- **Machine Learning**: `caret` and `randomForest` for building and evaluating the classification model.
- **Data Manipulation & Visualization**: `dplyr`, `tidyverse`, `ggplot2`, and `corrplot`.

## Project Structure

- `Clasificador_musical.Rmd`: The main notebook for training the Random Forest classifier, performing cross-validation, and evaluating model performance (Confusion Matrix, Feature Importance).
- `Extraccion_caracteristicas.Rmd`: Notebook dedicated to the comprehensive extraction of features from audio files across multiple genres.
- `Funciones_scripts_individuales/`: A directory containing various auxiliary scripts and experimental notebooks used during development for feature extraction and visualization.
- `features_*.csv`: Pre-extracted feature datasets for different genres (Country, Jazz, Opera, Rap, Reggae).

## Setup & Installation

To run this project, you will need R and Python installed. 

1. Install the required R packages:
   ```r
   install.packages(c("tuneR", "seewave", "caret", "randomForest", "ggplot2", "dplyr", "readr", "corrplot", "reticulate", "pacman"))
   ```
2. The project uses `reticulate` to set up a Conda environment for `librosa`. Running the feature extraction scripts will automatically attempt to configure this environment. Ensure you have Miniconda or Anaconda installed, or let `reticulate` handle the Miniconda installation.

## Usage

1. Place your `.wav` audio files into their respective genre directories.
2. Run `Extraccion_caracteristicas.Rmd` to process the audio files and generate the `features_[genre].csv` files.
3. Run `Clasificador_musical.Rmd` to train the model, view the confusion matrix, and analyze feature importance.
