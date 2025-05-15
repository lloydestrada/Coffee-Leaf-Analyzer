# Coffee Leaf Analyzer: Nutritional Stress Severity and Nutrient Deficiency Classification using CNNs

> **Authors**:  
John Aries U. Salvador¹, John Lloyd A. Estrada², Marc P. Laureta³  
(College of Informatics and Computing Studies, New Era University, Quezon City, 1107 Philippines)  
📧 johnaries.salvador@neu.edu.ph | johnlloyd.estrada@neu.edu.ph | mplaureta@neu.edu.ph

---

## Abstract

This project presents a **deep learning-based solution** to classify **nutrient deficiencies (N, P, K)** and **stress severity levels** in coffee leaves using **custom Convolutional Neural Networks (CNNs)**.

- **Model 1**: Classifies **nutrient deficiencies**: Healthy, Nitrogen, Phosphorus, and Potassium.
- **Model 2**: Detects **stress severity**: No Risk, Low, Medium, and High.
- Trained using the **CoLeaf dataset** and a **custom-processed stress dataset**.
- Achieved **95% accuracy** for nutrient classification and **85% for stress severity**.

---
## 📄 Research Paper

This project is based on our undergraduate research paper:

> **Title**: Nutritional Stress Severity and Nutrient Deficiency Classification in Coffee Leaves Using Convolutional Neural Networks  
> **Authors**: John Aries U. Salvador, John Lloyd A. Estrada, Marc P. Laureta  
> **Institution**: College of Informatics and Computing Studies, New Era University  
> 📄 **[View Paper on Google Docs](https://docs.google.com/document/d/13ZTcPESsC79hKdnHvVFM8RoXpGG9CIRgvUORB0G0jRY/edit?usp=sharing)**

If you find this work useful, feel free to explore, cite, or collaborate!

---
## Highlights

### Key Features
- Dual CNN architecture for:
  - Nutrient deficiency detection
  - Stress severity classification
- **Custom image preprocessing**:
  - Background removal
  - CLAHE in LAB color space
  - HSV/YCrCb segmentation for stress
- **Web-based application** with real-time leaf classification and visual feedback
- **Deployment**: Cloud-hosted Flask application using TensorFlow backend

### Model Details
- **Activation Functions**: ReLU (hidden layers), Softmax (output)
- **Regularization**: Batch normalization, dropout, L2 regularization
- **Training Enhancements**: Data augmentation, cosine learning rate decay
- **Frameworks Used**: TensorFlow, Keras, OpenCV, Flask

---

## Dataset

- Sourced from **Kaggle** for nutrient classification (4 classes)
- Custom-generated stress dataset via image processing pipeline
- Data split:
  - Nutrient: 70% train / 20% val / 10% test
  - Stress: ~3,100 train / ~890 val / ~460 test
- **Image size**: 224x224
- **Normalization**: Pixel values scaled to `[0, 1]`

---

## Performance

### Nutrient Deficiency Model
- **Test Accuracy**: 94.99%
- **Training Accuracy**: 99.98%
- **Validation Accuracy**: 86.77%

### Stress Severity Model
- **Test Accuracy**: 85.22%
- **Training Accuracy**: 95.19%
- **Validation Accuracy**: 94.38%

---

## System Design

### Workflow
1. **Upload** coffee leaf image via web UI
2. **Preprocessing** (resize, normalize)
3. **Dual model inference**
   - Nutrient deficiency classification
   - Stress severity detection
4. **Output**: Predictions + highlighted stress areas + care recommendations

### Web Application
- **Backend**: Flask + TensorFlow
- **Frontend**: HTML, CSS, JS
- **Libraries**: OpenCV, PIL
- **Deployment**: Cloud server with GPU support

---

## Setup Instructions

```bash
# Clone the repo
git clone https://github.com/ariessalvador/Coffee-Leaf-Analyzer.git
cd coffee-leaf-analyzer

# Create virtual environment and install requirements
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows
pip install -r requirements.txt

# Run the Flask app
python app.py
```

## Contact

For inquiries or collaboration, contact:

- 📧 **John Aries U. Salvador** – johnaries.salvador@neu.edu.ph  
- 📧 **John Lloyd A. Estrada** – johnlloyd.estrada@neu.edu.ph  
- 📧 **Marc P. Laureta** – mplaureta@neu.edu.ph  

---

## Acknowledgments

Special thanks to:

- **New Era University** – Institutional and technical support  
- **Kaggle Community** – For the initial nutrient deficiency dataset  
- **Coffee Research Institutes** – For reference imagery and documentation  
- **TensorFlow, Keras, and OpenCV** – For open-source frameworks powering the project

---

## Future Work

- Incorporate **attention mechanisms (e.g., CBAM or SE blocks)** for more precise classification
- Expand the dataset to include **secondary nutrient and micronutrient deficiencies**
- Develop a **mobile-friendly version** for offline field diagnosis
- Extend the model to support **other agricultural crops**

---

## Sample Output

![image](https://github.com/user-attachments/assets/01ad5649-0dab-40e5-bd0e-5166ac961fc8)


> *Example of the web app interface showing leaf classification results and stress region visualization.*

---

## Repository Structure

```text
coffee-leaf-analyzer/
├── Sample Images/              # Sample input images for testing
├── model/                      # Directory containing trained CNN models
│   ├── Severity_Main1.h5       # CNN model for stress severity prediction
│   └── nutrient_cnn_model.h5   # CNN model for nutrient deficiency classification
├── templates/                  # HTML templates for the web interface
├── .gitattributes              # Git configuration file for attributes
├── .gitignore                  # Specifies files to be ignored by Git
├── README.md                   # Project documentation
├── app.py                      # Main Flask application
└── requirements.txt            # List of Python dependencies
```


## Related Links

- [CoLeaf Dataset on Kaggle](https://www.kaggle.com/datasets/janmejaybhoi/coffee-leaf-dataset)
- [TensorFlow Documentation](https://www.tensorflow.org/)

---

##  License

This project is released under the **MIT License**. See the [LICENSE](./LICENSE) file for more details.

---

*© 2025 Coffee Leaf Analyzer Project – New Era University*
