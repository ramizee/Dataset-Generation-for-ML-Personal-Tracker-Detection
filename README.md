# Dataset Generation for ML Personal Tracker Detection

## Table of Contents
- [Introduction](#introduction)
- [Download Dataset](#download-dataset)
- [Running the Application](#running-the-application)
- [Files](#files)

## Introduction
This is the Master Thesis of Ramize Abdili, written from December 2023 till June 2024 with the Communication Sytsems Group of the University of Zurich (UZH). This thesis focuses on creating a large dataset of sniffed Bluetooth Low Energy (BLE) data packets for analysis and pattern recognition. Features are extracted from the dataset that are characteristics of a device type. These extracted features are used to train Machine Learning (ML) models to classify and identify various BLE devices based on their characteristics. The ML models used in this thesis are the Random Forest (RF) classifier and the Multi-Layer Perceptron (MLP) model.

## Download Dataset
The generated dataset is a CSV file and is needed in order to run the code locally. Since it is too large for GitHub, it can be downloaded from this OneDrive link:
- [Download Dataset (CSV)](https://uzh-my.sharepoint.com/:x:/r/personal/ramize_abdili_uzh_ch/Documents/MA/all_data_final.csv?d=wf7085933416b4bb2ad4dea7ab36cfda1&csf=1&web=1&e=tjfZiQ)

## Running the Application
Jupyter Notebook and Python v3.12 should be installed to run the application. All dependencies needed to run the application are included in the Python files. The file path to the dataset should be adjusted in the Python files to read the dataset correctly.

## Files
These following files should be excecuted in this following order:

1. **Results Initial BLE sniffing.ipynb**: It displays non-empty packets of device name, company ID, and UUID fields from CSV files where packets from public places are sniffed.
2. **CSV Info for Labeling devices.ipynb**: It displays unique field names of device name, company ID, and UUID fields for each CSV file. Based on these unqiue field names, labeling is done.
3. **Labeling.ipynb**: Each sniffed packet of each CSV file is labeled with its device type.
4. **Feature Extraction.ipynb**: To each CSV file which is labeled features are extracted. At the end all CSV files are merged together into one CSV file.
5. **Data Preprocessing & Data Splitting.ipynb**: The generated dataset is pre-processed and is split into training and test datasets according to the 80/20 and the alternative data splitting methods.
6. **Feature Selection Methods.ipynb**: The filter and embedded feature selection methods are shown. Applying both methods, the first 30 selected features are printed.
7. **Plotting of Results.ipynb**: The plots for the result chapter are shown, including results of chapters device collection, data collection, labeling, feature extraction and data splitting.
8. **MLP Installations.ipynb**: Provides the commands needed to install dependencies and packages for running the MLP model.

After exceuting these 8 files, the dataset is created. These following files which train the ML models can be excecuted in any order:

- **Random Forest 1.ipynb**: Shows the RF classifier trained on data created by the 80/20 data splitting method and also the evaluation metrics such as precision, recall, specificity, f1-score, confusion matrix. Furthermore, the accuracy of each device type is calculated and overfitting is checked by doing cross-validation.
- **Random Forest 1 with selected Features.ipynb**: Shows the RF classifier trained on data created by the 80/20 data splitting method and with selected features. It shows the best number of features with the highest accuracy.
- **Random Forest 2.ipynb**: Shows the RF classifier trained on data created by the alternative data splitting method and also the evaluation metrics such as precision, recall, specificity, f1-score, confusion matrix. Furthermore, the accuracy of each device type is calculated and overfitting is checked by doing cross-validation.
- **Random Forest 2 with selected Features.ipynb**: Shows the RF classifier trained on data created by the alternative data splitting method and with selected features. It shows the best number of features with the highest accuracy.
- **MLP1.ipynb**: Shows the MLP model trained on data created by the 80/20 data splitting method and also the evaluation metrics such as precision, recall, specificity, f1-score, confusion matrix. Furthermore, the accuracy of each device type is calculated and overfitting is checked by doing cross-validation. It also shows the MLP model trained on data created by the 80/20 data splitting method and with selected features. It shows the best number of features with the highest accuracy.
- **MLP2.ipynb**: Shows the MLP model trained on data created by the alternative data splitting method and also the evaluation metrics such as precision, recall, specificity, f1-score, confusion matrix. Furthermore, the accuracy of each device type is calculated and overfitting is checked by doing cross-validation. It also shows the MLP model trained on data created by the alternative data splitting method and with selected features. It shows the best number of features with the highest accuracy.
- **Further ML Models.ipynb**: Further ML models such as Decision Tree (DT), K-Nearest Neighbors (KNN), Support Vector Machine (SVM), Logistic Regression (LG), and Neural Network models are trained on the dataset created by using 80/20 data splitting method.