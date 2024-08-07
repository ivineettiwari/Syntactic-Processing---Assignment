# Disease and Treatment Extraction

## Overview

This project demonstrates a workflow for extracting, analyzing, and organizing information related to diseases and their treatments from a dataset. The following sections summarize the process, including data preparation, model training, and evaluation.

## Steps Performed

### Data Preparation and Feature Extraction

- **Sentence Conversion:** Sequences of words and labels were converted into sentences and sequences of labels, respectively.
- **Feature Extraction:** Features for each word in the sentences were extracted using the `getFeaturesForOneSentence` function. Features included the word itself, its part-of-speech tag, and its relationship with adjacent words.
- **Label Structuring:** Labels were converted into a structured list format for both training and testing datasets.

### Model Training

- **CRF Model:** A Conditional Random Field (CRF) model was initialized and trained on the extracted features and labels. This model was used to predict disease and treatment entities in sentences.

### Prediction and Evaluation

- **Prediction:** Predictions were made on the test dataset.
- **Evaluation:** The F1 score was calculated to evaluate the model's performance. The weighted F1 score provided an overall measure of how well the model performed in classifying disease and treatment entities.

### Entity Extraction

- **Entity Mapping:** Entities of interest (diseases and treatments) were extracted from the model’s predictions. A `disease_treatment` dictionary was constructed to map diseases to their corresponding treatments.
- **Dictionary Cleaning:** The dictionary was cleaned to remove entries where the treatment list was empty, resulting in a `cleaned_dict` that included only diseases with associated treatments.

### Data Visualization

- **DataFrame Creation:** A DataFrame was created from the cleaned dictionary to organize and visualize the relationship between diseases and their treatments.
- **Specific Search:** A search was performed for the disease "hereditary retinoblastoma" and its associated treatments were displayed.

## Output

For the specific search item "hereditary retinoblastoma," the output showed:
Treatments for 'hereditary retinoblastoma' are: 'radiotherapy'


## Summary

The process effectively demonstrated the end-to-end workflow of extracting features, training a CRF model, evaluating its performance, and organizing the results. The model successfully identified "hereditary retinoblastoma" and mapped it to its treatment, "radiotherapy." This showcases the model's capability to recognize and link medical entities, which is crucial for tasks such as medical information extraction and decision support in healthcare.
