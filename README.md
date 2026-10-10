# Galaxy Classifier

Neural network application for morphological classification of galaxies into **Spiral** and **Elliptical** types.

## Overview

This repository contains a pre-trained TensorFlow/Keras model and Gradio web interfaces for classifying galaxy images. Users can upload an image of a galaxy and receive a predicted morphological type along with a confidence score.

The model distinguishes between:
- **Spiral**
- **Elliptical**

(An updated notebook also supports an **Uncertain** class.)

## Repository Structure

| File / Folder | Description |
|---------------|-------------|
| `galaxyml_app.ipynb` | Gradio demo interface (binary: Spiral / Elliptical) |
| `galaxyml_app_updated.ipynb` | Updated Gradio interface (includes Uncertain class) |
| `model.pb` | TensorFlow SavedModel graph definition |
| `keras_metadata.pb` | Keras model metadata |
| `variables/` | Model weights (`variables.data-*` and `variables.index`) |

## Model

The repository includes a saved TensorFlow model in **SavedModel** format, ready for inference.

- Input: RGB images resized to **256×256**
- Preprocessing: pixel values normalized to `[0, 1]`
- Output: class probabilities (binary or 3-class depending on the notebook)

The model weights are stored in the `variables/` directory alongside `saved_model.pb` and `keras_metadata.pb`.
```bash
pip install tensorflow gradio opencv-python numpy
