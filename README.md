# Cat vs Dog Image Classification 🐱🐶

## Project Overview
This project builds a Convolutional Neural Network (CNN) using TensorFlow/Keras to classify images as either **Cat** or **Dog**.

The notebook performs:
- Dataset loading
- Image preprocessing and visualization
- Data normalization and splitting
- CNN model creation
- Model training and validation
- Performance evaluation
- Prediction on new images
- Model saving

## Technologies Used
- Python
- TensorFlow / Keras
- NumPy
- OpenCV
- Matplotlib

## Dataset
Dataset source:
`fusicfenta/cat-and-dog` (downloaded using KaggleHub)

Directory structure:
```
dataset/
├── training_set/
│   ├── cats/
│   └── dogs/
```
## Model Architecture

```text
Input: 256 x 256 x 3

Conv2D(32, 3x3, ReLU)
MaxPooling2D

Conv2D(64, 3x3, ReLU)
MaxPooling2D

Conv2D(128, 3x3, ReLU)
MaxPooling2D

Flatten

Dense(256, ReLU)
Dropout(0.5)

Dense(1, Sigmoid)
```

## Compilation

```python
model.compile(
    optimizer='adam',
    loss='binary_crossentropy',
    metrics=['accuracy']
)
```

## Training

```python
model.fit(
    train,
    epochs=25,
    validation_data=val
)
```

## Evaluation Metrics
- Accuracy
- Precision
- Recall

## Prediction

```python
yhat = model.predict(np.expand_dims(image/255, 0))
```

Output:
- Value close to 0 → Cat
- Value close to 1 → Dog

## Saved Model

```python
model.save('models/imageclassifier.h5')
```

## Results
The CNN learns image features through multiple convolutional layers and performs binary classification between cats and dogs.

## Author
Created as a Deep Learning Image Classification project using TensorFlow and Keras.

