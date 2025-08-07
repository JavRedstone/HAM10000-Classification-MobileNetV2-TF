# Skin Lesion Classification using HAM10000 Dataset
By: Javier H
Colab link: https://colab.research.google.com/drive/1nRPYG89MtCRq3KMUJHQtVbq7sAagepEv?usp=sharing

This project explores the use of deep learning to classify skin lesion images into seven diagnostic categories using the **HAM10000 (Human Against Machine with 10000 training images)** dataset. Skin cancer is one of the most common types of cancer globally, and early detection plays a vital role in improving patient outcomes. Automating diagnosis using machine learning can help dermatologists with faster and more consistent screening.

## Dataset Overview

The dataset used is the **HAM10000** dataset, publicly available on [Kaggle](https://www.kaggle.com/datasets/kmader/skin-cancer-mnist-ham10000). It contains **10,015 dermatoscopic images** of pigmented lesions, curated from multiple sources for the purpose of machine learning research.

### Classes (Skin Lesion Types):

| Label | Abbreviation | Meaning                                                                                       |
|-------|--------------|-----------------------------------------------------------------------------------------------|
| 0     | akiec        | Actinic keratoses and intraepithelial carcinoma/Bowen disease                                 |
| 1     | bcc          | Basal cell carcinoma                                                                          |
| 2     | bkl          | Benign lesions of the keratosis type (solar lentigine/seborrheic keratoses and lichen-planus like keratosis) |
| 3     | df           | Dermatofibroma                                                                               |
| 4     | mel          | Melanoma                                                                                    |
| 5     | nv           | Melanocytic nevi                                                                            |
| 6     | vasc         | Vascular lesions (angiomas, angiokeratomas, pyogenic granulomas and hemorrhages)             |

**Note:** The dataset is highly imbalanced, with 'nv' making up the majority of images. This imbalance will become a significant problem evident during model evaluation.

---

## Objective

To train a convolutional neural network (CNN) that can accurately classify dermatoscopic images into one of the seven skin lesion categories. Evaluation metrics include accuracy, loss, and confusion matrix analysis on a stratified test set.

---

## Why This Matters

Skin cancer detection is a domain where machine learning can provide real-world impact. Manual diagnosis by dermatologists is subject to visual fatigue and variation in interpretation. A robust, automated model can assist in triaging patients and identifying high-risk lesions early.

---

## Techniques Used

- **Transfer Learning** with pre-trained CNN backbones (e.g., EfficientNet, ResNet)  
- **Data Augmentation** to address class imbalance and overfitting  
- **Class-wise evaluation** using confusion matrices  
- **Validation and test split** to assess generalization  
- **Categorical cross-entropy loss** for multi-class classification  

---

## Dataset Splits

The dataset was split as follows:

- **Training Set**: ~70%  
- **Validation Set**: ~15%  
- **Test Set**: ~15%  

Splits were stratified to preserve class distribution across all subsets.

---

## Challenges

- Severe class imbalance (e.g., over 4600 images for `nv`, but fewer than 100 for `df`, `vasc`)  
- High visual similarity between certain lesion types (e.g., `bkl` vs `nv`)  
- Risk of overfitting on the dominant class  
- Limited test performance despite high training accuracy — highlighting the importance of robust evaluation  

---

## Outcomes

Despite good training performance, the model demonstrates reduced generalization on the test set, suggesting further work is needed in:

- Handling class imbalance (e.g., weighted loss, oversampling)  
- Improving augmentation strategies
- Fine-tuning on the MobileNetV2 backbone

Confusion matrix analysis was crucial for understanding which classes were most often misclassified and why.

---

## Credits

Dataset: [HAM10000 - Kaggle](https://www.kaggle.com/datasets/kmader/skin-cancer-mnist-ham10000)  
Original Challenge: [ISIC 2018 Challenge](https://challenge2018.isic-archive.com)  
Harvard Dataverse: [HAM10000 Dataset](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/DBW86T)  

Key references:  
1. Noel Codella, Veronica Rotemberg, Philipp Tschandl, M. Emre Celebi, Stephen Dusza, David Gutman, Brian Helba, Aadi Kalloo, Konstantinos Liopyris, Michael Marchetti, Harald Kittler, Allan Halpern:  
“Skin Lesion Analysis Toward Melanoma Detection 2018: A Challenge Hosted by the International Skin Imaging Collaboration (ISIC)”, 2018; [https://arxiv.org/abs/1902.03368](https://arxiv.org/abs/1902.03368)  

2. Tschandl, P., Rosendahl, C. & Kittler, H.  
The HAM10000 dataset, a large collection of multi-source dermatoscopic images of common pigmented skin lesions. Sci. Data 5, 180161 doi:10.1038/sdata.2018.161 (2018).