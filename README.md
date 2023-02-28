# DeepFake Detection App

> Streamlit app forked for debugging purposes only.

## 🚧 Currently under construction 🚧

## This [streamlit app](https://share.streamlit.io/filxy/deepfake-detection-app/main/app.py) is for deep fake detection

Upload an image and after the image is displayed click predict button.
It allows you to Capture image from webcam and predict on the webcam prediction page.
YouTube URL can be predicted by copy pasted the youtube url you want to detect on the YouTube Prediction page.
(Currently under construction).

## Issues

- Undefined methods in the `app.py` file
  - eval_js
  - imageio
  - face_recognition
- model `Meso4_DF` cannot be loaded for unknown reasons
  - maybe a mismatch between model definition and stored model
  - maybe wrong file format
- DeprecationWarnings
  - scipy
    - multiple usage of `scipy` methods with a DeprecationWarning
  - keras
    - The `lr` argument is deprecated, use `learning_rate` instead

## Bad practices

- uploaded images are stored in the root and `/test` folder
  - your file system will be filled up with images
  - this is a bad practice, use a temporary folder instead or keep the images in memory
- class definitions within `main` functions
  - bad practice, move all classes outside
- Conflicting imports
  - double import of class `Image` see below:

```python
from IPython.display import Image, Javascript, display
from PIL import Image
```
