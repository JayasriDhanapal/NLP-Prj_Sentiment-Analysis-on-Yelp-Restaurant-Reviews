# 🍽️ Sentiment Analysis on Yelp Restaurant Reviews
### Using Transformer-Based Models (RoBERTa)

##  Team Members
- **Jayasri Dhanapal**  
- **Divya Jayaprakash**  
- **Reshma Karthikeyan Nair**

## 📌 Project Overview
This project performs **multi-class sentiment analysis** on Yelp restaurant reviews using **transformer-based NLP models**. Reviews are classified into **five sentiment classes (1–5 stars)**.  
A **RoBERTa-base** model is fine-tuned on the full Yelp Review dataset and evaluated against a **BERT-based baseline**, achieving superior performance.

---

## 🎯 Objectives
- Perform **5-class sentiment classification** on Yelp restaurant reviews  
- Fine-tune **RoBERTa-base** on a large-scale dataset  
- Apply optimization techniques to train under limited resources  
- Compare results with a strong **BERT baseline model**

---

## 📂 Dataset
- **Dataset:** Yelp Review Full  
- **Source:** Hugging Face Datasets  
- **Training Samples:** 650,000  
- **Test Samples:** 50,000  
- **Labels:**
  - 1 ⭐ – Very Negative  
  - 2 ⭐ – Negative  
  - 3 ⭐ – Neutral  
  - 4 ⭐ – Positive  
  - 5 ⭐ – Very Positive  

---

##  Data Preprocessing
- Convert text to lowercase  
- Remove URLs  
- Normalize whitespace  
- Trim leading and trailing spaces  
- Parallel preprocessing for efficiency

---

##  Tokenization
- **Tokenizer:** RoBERTa tokenizer  
- **Maximum Sequence Length:** 128  
- **Truncation:** Applied for long reviews  

---

##  Model Architecture
### RoBERTa-base
- Transformer-based encoder model  
- ~125 million parameters  
- Pre-trained on large-scale English corpora  
- Classification head added for **5 sentiment classes**

---

## ⚙️ Optimization Techniques
- Mixed-precision training (**FP16**)  
- Gradient accumulation  
- Gradient checkpointing  
- Parallel preprocessing and tokenization  
- Reduced logging and checkpoint overhead  

---

##  Training Configuration

| Parameter | Value |
|--------|-------|
| Model | RoBERTa-base |
| Learning Rate | 2e-5 |
| Batch Size (per device) | 32 |
| Gradient Accumulation Steps | 2 |
| Effective Batch Size | 64 |
| Epochs | 2 |
| Weight Decay | 0.01 |
| Precision | FP16 |
| Hardware | Tesla T4 (Google Colab) |

---

## ⏱️ Training Time
- **Total Training Time:** 13,649 seconds (~3h 47m)  
- **Planned Steps:** 20,000  
- **Stopped At:** 14,000 (Colab time limit)  
- **Best Checkpoint:** Step 12,000  

---

## 📊 Evaluation Metrics
- Accuracy  
- Precision (weighted)  
- Recall (weighted)  
- F1-score (weighted)  
- Confusion Matrix  

---

## 📈 Results

### RoBERTa Model Performance
- **Accuracy:** 0.6701  
- **Weighted F1-score:** 0.6692  

| Class | Precision | Recall | F1-score |
|------|-----------|--------|----------|
| 1 star | 0.78 | 0.79 | 0.78 |
| 2 stars | 0.61 | 0.62 | 0.62 |
| 3 stars | 0.63 | 0.58 | 0.60 |
| 4 stars | 0.59 | 0.58 | 0.59 |
| 5 stars | 0.74 | 0.77 | 0.75 |

---

##  Baseline Model Performance (BERT)
- **Accuracy:** 0.6123  
- **Weighted F1-score:** 0.6153  

### Model Comparison
| Model | Weighted F1-score |
|------|------------------|
| BERT (Baseline) | 0.615 |
| RoBERTa (Proposed) | **0.669** |

---

##  Discussion
RoBERTa’s robust pretraining and optimized fine-tuning strategy significantly improve sentiment classification performance.  
Early training termination was caused by **Colab runtime limits**, not model convergence.

---

## ✅ Conclusion
This project demonstrates the effectiveness of **transformer-based models** for large-scale sentiment analysis.  
Efficient training strate
