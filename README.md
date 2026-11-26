# Plant Disease Detection using VGG16

A deep learning model that identifies plant leaf diseases from a photo. It classifies a leaf image into **38 classes** (diseased and healthy leaves across 14 crops) using **transfer learning with VGG16**, built with TensorFlow/Keras.

<!-- Add a screenshot of a correct prediction here, for example: -->
<!-- ![Sample prediction](samples/prediction_example.png) -->

## Why this project
Plant diseases reduce crop yield, and many farmers cannot get an expert diagnosis quickly. This project shows how a trained image classifier can give a fast first diagnosis from a single leaf photo.

## What it does
- Takes a leaf image as input
- Resizes it to 224 x 224 and normalizes it
- Predicts the disease (or "healthy") and shows the **confidence score**

Example output:
```
Disease :  TOMATO LATE BLIGHT
Confidence:  97.4 %
```
<!-- Replace the example above with a real output from your notebook. -->

## Model
| Item | Details |
|---|---|
| Architecture | VGG16 (transfer learning, ImageNet pretrained base) |
| Input size | 224 x 224 x 3 |
| Output | 38 classes (softmax) |
| Framework | TensorFlow / Keras |
| Training accuracy | **XX%** <!-- fill from your training notebook --> |
| Validation accuracy | **XX%** <!-- fill from your training notebook --> |
| Test accuracy | **XX%** <!-- fill if you evaluated on a test set --> |

## Classes (38)
Apple scab, Apple black rot, Cedar apple rust, Apple healthy, Blueberry healthy, Cherry powdery mildew, Cherry healthy, Corn cercospora leaf spot (gray leaf spot), Corn common rust, Corn northern leaf blight, Corn healthy, Grape black rot, Grape black measles, Grape leaf blight, Grape healthy, Orange huanglongbing (citrus greening), Peach bacterial spot, Peach healthy, Pepper bell bacterial spot, Pepper bell healthy, Potato early blight, Potato late blight, Potato healthy, Raspberry healthy, Soybean healthy, Squash powdery mildew, Strawberry leaf scorch, Strawberry healthy, Tomato bacterial spot, Tomato early blight, Tomato late blight, Tomato leaf mold, Tomato septoria leaf spot, Tomato spider mites (two-spotted spider mite), Tomato target spot, Tomato yellow leaf curl virus, Tomato mosaic virus, Tomato healthy.

## Repository structure
```
plant-disease-detection-vgg16/
├── training_vgg16.ipynb      # model training
├── inference_vgg16.ipynb     # load the model and predict on a leaf image
├── samples/                  # sample leaf images for testing
├── requirements.txt
├── .gitignore
├── LICENSE
└── README.md
```

## How to run

**1. Clone the repository**
```
git clone https://github.com/Chithrakarravula/plant-disease-detection-vgg16.git
cd plant-disease-detection-vgg16
```

**2. Install the requirements**
```
pip install -r requirements.txt
```

**3. Download the trained model**
The model file is too large for GitHub, so it is hosted separately:
**[Download vgg16model.h5](ADD-YOUR-MODEL-LINK-HERE)**
Place it in a folder called `models/` (so the path is `models/vgg16model.h5`).

**4. Run the inference notebook**
Open `inference_vgg16.ipynb`, set the model path to `models/vgg16model.h5`, and run the cells. Use any image from the `samples/` folder, or your own leaf photo.

You can also run it in Google Colab: upload the notebook and the model file, then update the paths.

## Results
<!-- Add 2 or 3 screenshots of correct predictions, and optionally a confusion matrix or accuracy/loss curves from training. -->

## Limitations
- The model only recognizes the **38 classes** it was trained on. If you give it a leaf with a disease outside this list (for example, downy mildew), it will still pick one of the 38 classes, sometimes with a very high confidence score. A high confidence does not guarantee a correct answer.
- The training images were taken in controlled conditions (a single leaf on a plain background). Accuracy can drop on photos taken in a real field with complex backgrounds, shadows or multiple leaves.
- This is a learning and demonstration project, not a replacement for advice from an agricultural expert.

## Future improvements
- Add an "unknown / not supported" option using a confidence threshold
- Test on real field photos and add data augmentation for them
- Compare VGG16 with lighter models (MobileNetV2, EfficientNet)
- Build a web app (Streamlit or Gradio) where a user uploads a leaf photo
- Add treatment suggestions for each detected disease

## Tech stack
Python, TensorFlow/Keras, NumPy, OpenCV, Matplotlib

## Acknowledgements
- **Dataset:** PlantVillage leaf disease dataset <!-- add the exact source link and check its license -->
- **Pretrained weights:** VGG16 trained on ImageNet, provided through Keras Applications

## License
This project's code is released under the [MIT License](LICENSE). The dataset and pretrained weights have their own terms.

## Author
**Chithra Karravula**
- GitHub: [Chithrakarravula](https://github.com/Chithrakarravula)
- LinkedIn: [ADD-YOUR-LINKEDIN-URL](ADD-YOUR-LINKEDIN-URL)
