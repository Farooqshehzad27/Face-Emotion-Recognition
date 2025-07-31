# 😊 Facial Emotion Recognition using CLIP

This project implements a Facial Emotion Recognition (FER) system using OpenAI's **CLIP Vision Transformer (ViT)**. The model classifies facial expressions into seven emotion categories using the FER2013 dataset. This work demonstrates the power of transfer learning in human-computer interaction applications.

---

## 📌 Project Overview

- **Model**: CLIP Vision Transformer (ViT) + Linear Classifier
- **Dataset**: FER2013
- **Emotion Classes**: Angry, Disgust, Fear, Happy, Sad, Surprise, Neutral
- **Image Size**: 48×48 (resized to 224×224 RGB)

---

## 🎯 Objectives

- ✅ Use the CLIP ViT model as a feature extractor for facial images
- ✅ Classify images into 7 emotions using a linear classifier
- ✅ Achieve good generalization on unseen data
- ✅ Evaluate performance using training/testing accuracy and loss

---

## 🗂️ Dataset: FER2013

- Total Images: **35,887** grayscale images (48×48 pixels)
- **Split**:
  - **Training Set**: Used for model training
  - **Testing Set**: Used for evaluation
- **Labels**:
  - `Angry`, `Disgust`, `Fear`, `Happy`, `Sad`, `Surprise`, `Neutral`

---

## 🔄 Data Preprocessing

- **Resize**: Images resized to `224x224`
- **Grayscale to RGB**: Converted to 3-channel grayscale
- **Normalization**:
  - Mean: `[0.5, 0.5, 0.5]`
  - Std Dev: `[0.5, 0.5, 0.5]`

---

## 🧠 Model Architecture

- **Feature Extractor**: CLIP Vision Transformer (ViT)
- **Classifier**: Single linear layer (`768 → 7`)
- **Frozen Weights**: CLIP parameters are frozen; only the classifier is trained

---

## 🏋️ Training Procedure

- **Loss Function**: CrossEntropyLoss
- **Optimizer**: Adam
- **Epochs**: 20
- **Training Loop**:
  - Forward pass → Loss computation → Backward pass
  - Track training and test metrics each epoch

---

## 📊 Training and Evaluation Results

| Epoch | Train Loss | Train Accuracy (%) | Test Loss | Test Accuracy (%) |
|-------|------------|--------------------|-----------|--------------------|
| 1     | 1.4832     | 43.21              | 1.4743    | 44.12              |
| 2     | 1.3456     | 48.75              | 1.3512    | 47.56              |
| 3     | 1.2345     | 51.23              | 1.2436    | 50.34              |
| ...   | ...        | ...                | ...       | ...                |
| 20    | 0.8764     | 65.45              | 0.9456    | 63.23              |

---

## 🔍 Observations

- **Training Progress**: Decreasing loss and increasing accuracy over epochs
- **Generalization**: Model performed well on the test set with improved accuracy
- **Best Accuracy**: Achieved **63.23%** test accuracy after 20 epochs

---

## ✅ Conclusion

This project demonstrates the effectiveness of using a pre-trained **CLIP ViT** model for emotion recognition tasks. The combination of transfer learning and lightweight linear classifiers enables fast training and reasonable performance on a small grayscale dataset.

### 📌 Future Work

- Fine-tune the CLIP model for further improvements
- Try different model architectures (ResNet, EfficientNet, etc.)
- Use larger or more balanced datasets for better generalization

---

## 🧠 Author

- **Farooq Shehzad**  
  [GitHub](https://github.com/Farooqshehzad27)

---

## 📄 License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.
