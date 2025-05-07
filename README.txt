# AI Multilingual Chatbot for Lung Cancer Detection

![Chatbot Flow](Chatbot%20flowchart.png)

An end-to-end intelligent medical assistant that detects lung cancer from CT scan images and generates multilingual, patient-friendly medical reports. Built using deep learning, NLP, and image validation models, this chatbot improves early detection and accessibility for patients worldwide.

---

## Features

- Swin Transformer for predicting malignancy scores (regression) from lung CT scans  
- ViT + CLIP to validate uploaded images and reject non-lung or non-medical images  
- Meta's NLLB for translating medical reports into 50+ languages  
- BioBERT for answering health-related questions in natural language  
- Streamlit chatbot interface for real-time interaction  
- Exportable PDF reports with malignancy score, risk level, and next steps  
- Doctor consult link for follow-up via telehealth

---

## Technologies Used

- PyTorch, Torchvision
- Transformers by Hugging Face
- Streamlit
- CLIP by OpenAI
- Swin Transformer, ViT, BioBERT, NLLB
- OpenCV, pydicom, PIL

---

## Repository Structure

├── app.py                     # Streamlit chatbot application  
├── app.ipynb                  # Notebook version of app.py  
├── vit.ipynb                  # ViT training notebook for lung/non-lung classifier  
├── test_ct_validation.py      # Testing script for ViT classification  
├── requirements.txt           # Required Python packages  
├── Chatbot flowchart.png      # Flow diagram for chatbot pipeline  
├── Research Design.png        # Research blueprint  
├── Swin_Tranformer_Model.png  # Swin Transformer training overview

---

## Model Overview

- Model: Swin Transformer Tiny  
- Input: 224×224 axial CT slices (PNG format)  
- Output: Continuous malignancy score (regression)  
- Loss: Mean Squared Error (MSE)  
- Optimizer: Adam (lr = 1e-4)  
- Dataset: LIDC-IDRI (First 100 patients)  
- Preprocessing: DICOM → PNG + Histogram Equalization

---

## Model Evaluation

| Metric | Score     |
|--------|-----------|
| MSE    | 0.0192    |
| MAE    | 0.0500    |
| R²     | 0.9872    |

---

## How to Run the App

### Install Requirements
pip install -r requirements.txt

### Run the Chatbot Locally
streamlit run app.py

Upload a lung CT image (PNG/JPG) and select your preferred language to generate the medical report and ask questions.

---

## Languages Supported

Supports 50+ languages including Hindi, Telugu, French, Tamil, Arabic, Spanish, Chinese, and more, using Meta’s NLLB-200 model.

---

## Screenshots

![Design](Research%20Design.png)

---

## Reference Models

- https://arxiv.org/abs/2103.14030 (Swin Transformer)
- https://arxiv.org/abs/1901.08746 (BioBERT)
- https://openai.com/research/clip (CLIP)
- https://ai.facebook.com/research/no-language-left-behind/ (NLLB-200)
- https://wiki.cancerimagingarchive.net/display/Public/LIDC-IDRI (LIDC-IDRI Dataset)

---

## License

This project is open-source under the MIT License.

---

## Acknowledgments

Thanks to the open-source community and public datasets like LIDC-IDRI for making this possible.