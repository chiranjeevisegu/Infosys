# 🏥 Radiology Image Captioning Project 📝

**Automatically generate descriptive captions for medical radiology images using deep learning!**

---

## 📌 Overview
This project implements an **AI-powered radiology image captioning system** using **VGG16** for image feature extraction and an **LSTM-based sequence model** for generating human-readable captions. It processes the **ROCO (Radiology Objects in Context) dataset** to train a model that can describe medical images accurately.

🔹 **Why this matters?**
- Helps in **automating medical report generation**
- Assists radiologists in **quick documentation**
- Useful for **medical education & training**

---

## 🛠️ Features

### 🖼️ **Image Processing**
- **VGG16 CNN** for extracting deep features from radiology images
- Image preprocessing (resizing, normalization)

### 📜 **Text Processing**
- Tokenization & sequence generation using **Keras Tokenizer**
- Padding for fixed-length captions

### 🤖 **Deep Learning Model**
- **CNN (VGG16) + LSTM** hybrid architecture
- Attention mechanism (optional) for better caption accuracy
- Custom training loop with progress tracking

### 📊 **Training & Evaluation**
- **GPU-accelerated training** (compatible with Kaggle/Colab)
- **Progress bars** (`tqdm`) for monitoring long-running tasks
- **Model checkpointing** to save best weights

---

## 📂 Dataset

### **ROCO Dataset** 🏷️
- **Source:** [Kaggle - ROCO Dataset](https://www.kaggle.com/datasets/virajbagal/roco-dataset)
- **License:** CC0-1.0 (Public Domain)
- **Size:** ~6.19GB (65,000+ medical images)
- **Structure:**
```
all_data/
├── validation/
│   └── radiology/
│       └── images/ (JPEG format)
```

---

## ⚙️ Setup & Installation

### **Prerequisites**
- Python 3.7+
- GPU recommended (for faster training)

### **Install Dependencies**
```bash
pip install tensorflow numpy tqdm pillow pandas matplotlib
```

### **Download Dataset**
The notebook automatically downloads and extracts the dataset using Kaggle API.

---

## 🚀 How to Run

### **Open the Notebook**
Run in Google Colab / Kaggle Notebooks / Jupyter Lab

### **Execute Cells Sequentially**
The notebook handles:
- ✅ Dataset download & extraction
- ✅ Image preprocessing
- ✅ Model training

### **Train & Evaluate**
- Monitor progress with `tqdm` bars
- Model weights are saved automatically

---

## 📈 Model Architecture

1. **Image Encoder (VGG16)**
   - Pretrained on ImageNet
   - Extracts 4096-dim feature vectors

2. **Text Decoder (LSTM)**
   - Generates captions word-by-word
   - Embedding layer for text processing

3. **Combined Model**
```python
Model: "image_captioning"
________________________________________________________
Layer (type)            Output Shape         Connected to                     
=================================================================
input_img (InputLayer)  [(None, 4096)]       VGG16 Features                  
input_txt (InputLayer)  [(None, max_len)]    Tokenized Text                  
embedding (Embedding)   (None, max_len, 256) input_txt                       
lstm (LSTM)            (None, 256)          embedding                       
dense (Dense)          (None, vocab_size)   lstm + input_img                 
=================================================================
```

## 🖼️ Sample Output:
Below are two sample outputs from the radiology image captioning model. [Replace the placeholders with your actual image paths or descriptions.]

- **Sample Image 1**:  
  ![Sample Radiology Image 1](![image](https://github.com/user-attachments/assets/ecfe0717-d47e-4792-a0fc-15a95f84eae0)
)  
  *Caption*: [Insert model-generated caption here, e.g., " thickening of the pyloric wall with an intramural fluid collection (white arrow) black arrow represents gall bladder."]

## 🎯 Applications

### **Medical Use Cases**
- ✔ **Automated Reporting** – Generate preliminary radiology notes
- ✔ **Education** – Help students learn radiology with AI-generated descriptions
- ✔ **Research** – Dataset can be used for other medical AI tasks

### **Future Improvements**
- 🔹 Attention Mechanism for better caption accuracy
- 🔹 Larger Pretrained Models (ResNet, ViT)
- 🔹 Multimodal Fusion (combine X-rays, CT scans, and reports)

---

## 📜 License

### **Code**
MIT License

Copyright (c) [Year] [Your Name]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

### **Dataset**
CC0-1.0 (Public Domain)
