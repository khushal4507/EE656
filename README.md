# 🛡️ ISTVT: Image-Spatial & Temporal Vision Transformer for Deepfake Detection  
**Finalist Project | EE656 Course (IIT Kanpur)**  
**Timeline:** July 2025  
**Mentor:** Prof. Nishchal K. Verma  

---

## 📌 Project Overview  
Developed a **transformer-based deepfake detector** that captures subtle spatial artifacts (e.g., blurred textures) and temporal inconsistencies (e.g., frame flickering) in synthetic videos. The ISTVT architecture combines **Xception-based tokenization** with **decomposed spatial-temporal attention**, achieving **88.75% validation accuracy** on the FaceForensics++ benchmark.  

---

## 🎯 Objective  
* Detect AI-manipulated videos by modeling **joint spatial-temporal patterns** missed by frame-based CNNs.  
* Provide **interpretable predictions** via attention heatmaps highlighting manipulated regions/timestamps.  

---

## 🧠 Approach  
### 1. **Architecture Design (ISTVT)**  
   - **Spatial Tokenization**: Xception network extracts features → converts frames to patch tokens.  
   - **Decomposed Attention**:  
     - *Spatial Attention*: Analyzes texture artifacts within frames.  
     - *Temporal Attention*: Detects inter-frame inconsistencies (enhanced by **self-subtract mechanism**).  
   - **Efficiency**: Reduces complexity from 𝒪(𝑇²𝐻²𝑊²) to 𝒪(𝑇² + 𝐻²𝑊²).  

### 2. **Interpretability**  
   - Generated spatial-temporal heatmaps using **Layer-wise Relevance Propagation** to visualize decision logic.  

### 3. **Data Pipeline**  
   - Preprocessed 400 videos (200 real + 200 fake) from **FaceForensics++**:  
     - Extracted 10 frames/video using **MTCNN face alignment**.  
     - Resized frames to `224×224` and stored as PyTorch tensors.  

### 4. **Training**  
   - **Optimizer**: Adam (`lr=1e-4`).  
   - **Loss**: Binary Cross-Entropy.  
   - **Batch Size**: 4 (15 epochs).  

---

## 📈 Key Results  
| Metric                     | Value     |  
|----------------------------|-----------|  
| **Peak Validation Accuracy** | 91.25%    |  
| **Best Validation Accuracy**| 88.75%    |  
| **Validation Loss**        | 0.2214    |  
| **Training Accuracy**      | 98.12%    |  

> 💡 Achieved **stable generalization** (85–90% val accuracy) with minimal overfitting.  

---
🛠️ Skills & Tools
-Deep Learning: PyTorch, Transformers, Vision Models
-Computer Vision: MTCNN, OpenCV, Feature Extraction
-Data Processing: Video Sampling, Face Alignment
-Analysis: Attention Visualization, Model Interpretability
