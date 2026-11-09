# Cat vs Dog Image Classifier (CNN)

A convolutional neural network built with TensorFlow and Keras that looks at a photo and says whether it shows a cat or a dog.

Built with Python, TensorFlow, Keras, OpenCV and Matplotlib. Developed with help from Claude.

## What it does

- Loads the Dogs vs Cats image dataset from Kaggle.
- Scales every image to the 0 to 1 range and resizes it to a fixed square size.
- Trains a CNN to separate the two classes.
- Plots training and validation accuracy and loss for each epoch.
- Predicts the class of a single image that you choose.

## Model

| Layer | Details |
| --- | --- |
| Conv2D + BatchNormalization + MaxPooling | 32 filters, 3x3, ReLU |
| Conv2D + BatchNormalization + MaxPooling | 64 filters, 3x3, ReLU |
| Conv2D + BatchNormalization + MaxPooling | 128 filters, 3x3, ReLU |
| Flatten | |
| Dense + Dropout | 128 units, ReLU, dropout 0.1 |
| Dense + Dropout | 64 units, ReLU, dropout 0.1 |
| Dense | 1 unit, sigmoid |

Training settings: Adam optimizer, binary cross-entropy loss, batch size 32, 10 epochs.

The output is a number between 0 and 1. Classes are sorted alphabetically, so `cats` is 0 and `dogs` is 1. A value close to 0 means cat and a value close to 1 means dog.

## Dataset

[Dogs vs Cats on Kaggle](https://www.kaggle.com/datasets/salader/dogs-vs-cats). The folder layout is:

```
catsvsdogs/
  train/
    cats/
    dogs/
  test/
    cats/
    dogs/
```

Point the training data at the `train` folder and the validation data at the `test` folder. Each one must contain exactly two class folders.

## How to run

1. Install the libraries:
   ```
   pip install tensorflow opencv-python matplotlib
   ```
2. Download the dataset (needs a Kaggle account and your `kaggle.json` API key):
   ```
   kaggle datasets download -d salader/dogs-vs-cats
   ```
   Unzip it and update the folder paths in the notebook.
3. Open the notebook in Jupyter or Google Colab and run the cells in order.
4. Training is slow on a CPU. Google Colab with a free GPU is much faster. You can also lower `image_size` to make each epoch quicker.

## Predict a single image

Set `image_path` in the last cell of the notebook to any cat or dog photo and run it. The notebook shows the image, prints the raw model output and prints the predicted class.

## Results

<!-- After retraining, add your validation accuracy and a screenshot of the accuracy and loss plots here. -->

## Author

Sahla Nawra V.P.
[LinkedIn](https://www.linkedin.com/in/sahla-nawra-978242273) | [GitHub](https://github.com/sahlanaurah-ux)
