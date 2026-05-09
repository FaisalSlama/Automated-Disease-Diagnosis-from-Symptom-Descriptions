# 🩺 Automated Disease Diagnosis from Symptom Descriptions

## 📌 Project Overview
This project presents an **AI-powered system for predicting diseases** from **free-text, patient-style symptom descriptions** using advanced **Natural Language Processing (NLP)** techniques.  
Unlike traditional models that rely on structured or short-text inputs, this system is designed to understand **real-world, unstructured patient language** and provide accurate predictions across **24 disease categories**.

The final pipeline integrates **transformer-based models (BERT, ClinicalBERT, BioBERT, RoBERTa)**, **Named Entity Recognition (NER)**, and **data augmentation using LLMs**, achieving:

- ✅ **95% test accuracy**  
- ✅ **96% validation accuracy**  
- ✅ **100% Top-3 accuracy on real-world simulated patient cases**

The system is deployed in a **web interface**, making it accessible for **telemedicine and patient-facing applications**.

---

##  Features
- 📝 **Free-text symptom input** → handles unstructured, natural patient descriptions.  
- 🤖 **Transformer-based classification** → fine-tuned BERT, BioBERT, ClinicalBERT, PubMedBERT, and RoBERTa models.  
- 🔍 **NER-enhanced predictions** → integrates biomedical entities for improved robustness.  
- 🧠 **Data augmentation with LLMs** → expanded dataset with 240+ clinically validated symptom variations.  
- 🌐 **Web deployment** → real-time predictions with disease summaries and follow-up guidance.  

---

## 🛠️ Tech Stack
- **Programming**: Python  
- **Libraries/Frameworks**: Hugging Face Transformers, TensorFlow, Scikit-learn, SpaCy, SciSpacy, Pandas, NumPy  
- **Models**: BERT-base, ClinicalBERT, BioBERT, PubMedBERT, RoBERTa, Logistic Regression, Random Forest, BiomedBERT  
- **Deployment**: Django + Web Interface  
- **Version Control**: Git/GitHub  

---

## 📂 Project Structure
```bash
├── data/               # Dataset (Symptom2Disease )  
├── MedicalAi/          # Web Deployment files
├── MedicalAi/requirements.txt     # Dependencies  
├── model/              # Fine-tuned transformer models
├── 24-Disease          # detailed information about diseases
├── disease_ai_pipeline.ipynb      # Ai Model
├── README.md           # Project documentation  
```
---

### 📓 Understanding `Disease_Ai_Pipeline.ipynb` 

The file `disease_ai_pipeline.ipynb` contains the **core training and evaluation workflow** for the AI disease prediction model. It documents each stage of the machine learning pipeline, making it easy to follow, reproduce, or extend the system.

**Key steps covered in the notebook:**
- **Data Preparation**: Load, inspect, clean, and structure the dataset for model training.  
- **Named Entity Recognition (NER)**: Enhance the dataset with biomedical entities using SciSpaCy and transformer-based NER pipelines.  
- **Model Pipeline (BERT & Variants)**: Tokenization, encoding, and fine-tuning transformer models such as BERT, BioBERT, ClinicalBERT, and RoBERTa.  
- **Training Process**: Train/validation/test splits, training arguments, and loss/accuracy tracking.  
- **Evaluation**: Evaluate models on test data, including accuracy, precision, recall, and F1 scores.  
- **Model Saving**: Save trained models and tokenizers for deployment in the web interface.  

👉 This notebook is the **heart of the AI system**, serving as both the development log and the reproducible workflow for generating disease prediction models.

## 📄 24-Disease.json
The file 24-Disease.json contains detailed information for each of the 24 diseases the model can predict. It includes:
- name → Disease name (e.g., “Acne”, “Fungal infection”).
- description → A brief overview of the disease.
- homeCare → Self-care and home remedies.
- medications → Recommended medications and their common side effects.
- lifestyle → Lifestyle tips to manage or prevent the disease.
- whenToSeeDoctor → Guidelines on when to seek professional medical attention.
  
#### The web interface uses this JSON file to display detailed disease information after a prediction. This allows the system to not only identify the disease but also provide educational and actionable guidance for users.
---

## ⚙️ Installation & Setup

1. Clone the repository:

   ```bash
   git clone https://github.com/V8FS1/Automated-Disease-Diagnosis-from-Symptom-Descriptions.git
   cd Automated-Disease-Diagnosis-from-Symptom-Descriptions
   ```

2. Create a virtual environment and install dependencies
   Option A — Python venv (recommended)

   macOS / Linux
   ```bash
   # from the project root
   python3 -m venv .venv
   source .venv/bin/activate
   python -m pip install --upgrade pip
   pip install -r requirements.txt
   ```
   Windows (PowerShell)
   ```bash
   # from the project root
   python -m venv .venv
   .venv\Scripts\Activate
   python -m pip install --upgrade pip
   pip install -r requirements.txt

   ```
3. Database Setup
   ```bash
   python manage.py migrate
   ```
4. Launch the Development Server:
   ```bash
   python manage.py runserver
   ```

---

## ⚙️ Using the AI Model
To use the disease prediction AI, you must download the pre-trained model files because they are not included directly in the repository (due to their large size).

### Steps to Download the Model
1. The project includes a Python script called download_model.py.
2. Run the script from your project root:
   ```bash
   python download_model.py
   ```
3. This will automatically download the required model files from Google Drive and place them in the appropriate folder (model/).
4. After downloading, the AI system is ready to use with the symptom input interface.
   
---

## 📊 Results For best Models

| Model                        | Test Accuracy | Real-World Top-1 | Real-World Top-3 |
| ---------------------------- | ------------- | ---------------- | ---------------- |
| ClinicalBERT (Text + NER)    | 90.3%         | 87.50%           | 100%             |
| BioMedBERT + NER             | 90.4%         | 89.58%           | 95.8%            |
| **RoBERTa + NER**            | **95.0%**     | **95.8%**        | **100%**         |

---

## 🎯 Use Cases

* **Telemedicine platforms** → AI-assisted triage for remote diagnosis.  
* **Healthcare chatbots** → symptom-based disease prediction.  
* **Clinical decision support** → assist doctors in primary care or emergency triage.  

---

## 📖 Future Work

* Expand dataset with real patient narratives.  
* Add **multilingual support** for global healthcare.  
* Integrate **clinical metadata** (age, gender, vitals) for personalized predictions.  
* Improve **model interpretability** for clinicians.  
* Conduct **real-world clinical trials** for validation.  

---

## 👤 Author

**Faisal Salama**  
B.Sc. Software Engineering | Üsküdar University  
📧 Email: [faisalslamav8@gmail.com](mailto:faisalslamav8@gmail.com)  
🔗 LinkedIn: www.linkedin.com/in/salamafaisal 
💻 GitHub: [FaisalSlama]([https://github.com/V8FS1](https://github.com/FaisalSlama))  

