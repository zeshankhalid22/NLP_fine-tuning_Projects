# NLP Project # 3  
### Transformer-Based NLP Tasks — GPT-2, BERT, and T5  

---

## **Q1: Fine-Tuning BERT for Customer Sentiment Analysis**

**Goal:**  
Build a lightweight classifier to detect positive/negative customer feedback.

**Dataset:**  
[Customer Feedback Dataset (Kaggle)](https://www.kaggle.com/datasets/vishweshsalodkar/customer-feedback-dataset) — 96 cleaned samples.

**Model Setup:**  
- Model: `bert-base-uncased`  
- Train/Validation Split: 77 / 19  
- Epochs: 3  
- Batch Size: 8  
- Max Sequence Length: 128  

**Results:**

| Metric | Score |
|:--------|:------:|
| Accuracy | **94%** |
| F1-Score | **94%** |

**Example:**  
> “Delivery was slow but the item works perfectly.”  
> **→ Predicted:** Negative (Confidence: 96%)

**Takeaway:**  
Transfer learning enables fine-tuning large models like BERT even with small datasets, achieving strong generalization.

---

## **Q2: Translating Pseudocode to Real Code using GPT-2**

**Goal:**  
Fine-tune GPT-2 to translate structured pseudocode into C++-style source code.

**Dataset:**  
[SPOC Dataset](https://github.com/sumith1896/spoc) — 64,224 cleaned pseudocode–code pairs.

**Model Setup:**  
- Model: `GPT-2 (small)`  
- Objective: Causal Language Modeling  
- Epochs: 3  
- Learning Rate: 5e-5  
- Batch Size: 2  
- Mixed Precision: fp16  

**Example:**

| Pseudocode | Generated Code | Ground Truth |
|-------------|----------------|---------------|
| `increase temp by (i - 1) * a` | `temp += (i - 1) * a;` | `temp += (i - 1) * a;` |

**Evaluation:**  
- BLEU Score: **0.4195**

**akeaway:**  
Decoder-only models like GPT-2 can perform structured translation tasks when fine-tuned with proper tokenization and data formatting.

---

## **Q3: Fine-Tuning T5 for News Summarization**

**Goal:**  
Generate concise, abstractive summaries of news articles using T5-small.

**Dataset:**  
[CNN/DailyMail Summarization](https://www.kaggle.com/datasets/gowrishankarp/newspaper-text-summarization-cnn-dailymail)

**📉 Training Metrics:**

| Epoch | Train Loss | Val Loss | Rouge-1 | Rouge-2 | Rouge-L |
|:--:|:--:|:--:|:--:|:--:|:--:|
| 3 | 1.64 | 1.54 | 0.42 | 0.21 | 0.29 |

**Example:**

| Section | Content |
|:---------|:--------|
| **Original Article** | Some teenagers get driving lessons from their parents. Other teens are ... |
| **Generated Summary** | Michelle Obama said Secret Service agents taught her daughter Malia how to drive. Mrs. Obama hasn’t driven in years. |

**Takeaway:**  
Even compact encoder-decoder models like T5-small can produce high-quality summaries efficiently with limited epochs.

---

## **Overall Summary**

| Task | Model | Goal | Key Metric |
|------|--------|------|-------------|
| Q1 | GPT-2 | Pseudocode → Code | BLEU = 0.4195 |
| Q2 | BERT | Sentiment Analysis | Accuracy = 94% |
| Q3 | T5 | Summarization | Rouge-1 = 0.42 |

---

## **Tech Stack**
- Python  
- Hugging Face Transformers  
- PyTorch  
- Polars  
- Scikit-learn  

---

### Authors
**Zeshan Khalid**  
**Zahid Aslam**
