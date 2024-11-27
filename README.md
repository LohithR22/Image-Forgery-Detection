# **Image Forgery Detection**

## **Overview**
The Image Forgery Detection project focuses on identifying and localizing digitally altered images to ensure the integrity and reliability of visual content. Leveraging deep learning techniques, the project tackles forgery detection using methods like copy-move and splicing. It incorporates two pre-trained CNN models—ResNet50 and DenseNet121—for classification and a ResNet-based localization model to detect tampered regions in images.

---

## **Key Features**
1. **Forgery Classification**: Classifies images as either authentic or forged using pre-trained ResNet50 and DenseNet121 architectures.
2. **Forgery Localization**: Identifies and masks tampered regions using a ResNet-based feature extractor and decoder network.
3. **Comparative Analysis**: Provides performance comparisons between ResNet50 and DenseNet121 based on F1 scores and parameter efficiency.

---

## **Dataset**
The dataset is a combination of multiple pre-existing datasets, split 70:30 for training and validation:
- **CASIA.V2**: 7,492 authentic and 5,123 forged images.
- **Columbia Uncompressed Image Splicing Detection Dataset**: 183 authentic and 180 forged images.
- **Image Manipulation Dataset**: 48 authentic and 48 forged images.
- **COMOFO Dataset**: 5,003 authentic and 5,000 forged images.

Image dimensions: **224x224**  
Number of categories: **2 (Authentic, Forged)**

---

## **Technical Details**
### **Models**
1. **ResNet50**:
   - Total Parameters: 23M
   - F1 Score: 81%
   - Architecture includes layers for feature extraction and dense layers for classification.
2. **DenseNet121**:
   - Total Parameters: 77M
   - F1 Score: 83%
   - Uses dense connections for efficient feature reuse.

### **Localization Model**
- **ResNet Feature Extractor**: Generates feature maps at multiple scales.
- **Decoder Network**: Processes feature maps with upsampling, convolution, and batch normalization to produce the forgery mask.

### **Experimental Results**
- ResNet50 and DenseNet121 demonstrated robust performance in detecting forgeries, with ResNet50 achieving a higher F1 score, while DenseNet121 showed better parameter efficiency.

---

## **Limitations**
- The dataset includes only splicing and copy-move forgeries, limiting its applicability to other types of forgery.
- Localization model results need improvement with further training and tuning.
- Models are not yet tested on real-world data.

---

## **Future Work**
1. Explore different loss functions and advanced training strategies for better accuracy.
2. Train the localization model on larger datasets with diverse forgery types for improved mask generation.
3. Implement the system for real-world use cases with real data testing.

---

## **Acknowledgments**
- **Libraries**: TensorFlow, Keras, NumPy, Matplotlib
- **Datasets**: CASIA.V2, CUISDE, Image Manipulation Dataset, COMOFO Dataset
