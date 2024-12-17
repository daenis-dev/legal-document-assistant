# Legal Document Service

### Overview

- A collection of scripts that is used to sort legal documentation



### Set Up

- Download the code repository

- Create a virtual environment

  ```
  python venv env
  ```

- Install the required dependencies

  ```
  pip install -r requirements.txt
  ```



### Use

- Start a Jupyter notebook

  ```
  jupyter notebook
  ```

- Run the scripts within *train-test.ipynb* in the sequence that they appear.
  - Convert PDF files to images
  - Split data into train and test
  - Create a wrapper for the image dataset
  - Augment and transform image data through the image dataset wrapper
  - Load the pretrained model and replace the final layer to output binary classification
  - Configure early stopping to avoid overfitting, train the model and save the model
  - Evaluate the model against the test set
  - Use the model to sort through local files



### Local Performance Evaluation Results

- Confusion matrix metrics
  - 8 items correctly classified as non-bankruptcy
  - 5 items correctly classified as bankruptcy
  - 5 items incorrectly classified as bankruptcy (items are actually non bankruptcy)
- Performance Summary
  - Recall for bankruptcy files: 1.0 (did not classify 'bankruptcy' files as 'non-bankruptcy')
  - Precision for bankruptcy files: 0.5 (classified 50% of 'non-bankruptcy' files as 'bankruptcy')
  - All files in the 'non-bankruptcy' directory were correct; half of the files in 'bankruptcy' were incorrect

- Recommended Use
  - This system should be used to separate about half of the non-bankruptcy files from a directory of legal files