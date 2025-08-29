# Assamese Text Summarization using LLaMA3-70B

## 📌 Project Overview
This project focuses on **Automatic Text Summarization for Assamese Language**, a low-resource language, using **Prompt Engineering techniques** with the **LLaMA3-70B model**.  
The goal is to generate concise and meaningful summaries for Assamese news articles and evaluate them using **ROUGE** and **BERTScore** metrics.

---

## 📂 Dataset
We collected datasets from **Kaggle** containing Assamese news articles:
- **News18** → 6,000 articles  
- **NENow** → 17,000 articles  

For evaluation, we created a custom dataset by generating summaries for **100 random articles** using different prompting techniques.

---

## 🔧 Methodology
The project follows a structured pipeline:

1. **Preprocessing**  
   - Cleaning and formatting Assamese text.  

2. **Prompt Engineering with LLaMA3-70B**  
   - **Zero-Shot Prompting** → Directly generating summaries without examples.  
   - **Few-Shot Prompting** → Providing sample summaries as context.  
   - **Chain-of-Thought (CoT)** → Encouraging step-by-step reasoning before summarization.  

3. **Evaluation Metrics**  
   - **ROUGE-1, ROUGE-2, ROUGE-L** → Based on n-gram overlap.  
   - **BERTScore** → Semantic similarity using contextual embeddings.  

4. **Error Analysis**  
   - Identified issues such as **loss of context, overgeneralization, and hallucination**.  

---

## 📊 Results

### ROUGE Score Breakdown
| Metric   | Score Type | Zero-Shot | Few-Shot | Chain-of-Thought |
|----------|------------|-----------|----------|------------------|
| ROUGE-1  | Precision  | 0.72      | 0.63     | 0.65             |
|          | Recall     | 0.74      | 0.70     | 0.69             |
|          | F1-Score   | 0.73      | 0.66     | 0.67             |
| ROUGE-2  | Precision  | 0.68      | 0.60     | 0.62             |
|          | Recall     | 0.69      | 0.65     | 0.64             |
|          | F1-Score   | 0.68      | 0.62     | 0.63             |
| ROUGE-L  | Precision  | 0.71      | 0.62     | 0.64             |
|          | Recall     | 0.73      | 0.68     | 0.67             |
|          | F1-Score   | 0.72      | 0.65     | 0.66             |

### BERTScore Comparison
| Metric     | Zero-Shot | Few-Shot | Chain-of-Thought |
|------------|-----------|----------|------------------|
| Precision  | 0.78      | 0.74     | 0.75             |
| Recall     | 0.79      | 0.77     | 0.76             |
| F1-Score   | 0.79      | 0.76     | 0.76             |

---

## 🔍 Observations
- **Zero-Shot** prompting surprisingly outperformed Few-Shot and CoT.  
- Possible reason → Assamese summaries are **simple, factual, and concise**, aligning better with Zero-Shot outputs.  
- **ROUGE** scores were relatively lower due to its reliance on word overlap, while **BERTScore** captured semantic similarity more effectively.  

---

## 🚀 Web Application
- Developed a **Flask-based web app** where users can input Assamese news text and generate summaries using different prompts.  
- Summaries are displayed with their **evaluation metrics** for analysis.  

---

## 📈 Future Work
- **Prompt Optimization** → Improve phrasing and structure of Few-Shot and CoT prompts.  
- **Domain-Specific Summarization** → Design prompts for specific domains (politics, health, etc.).  
- **Larger Evaluation Dataset** → Use more diverse news datasets for robust testing.  
- **Fine-Tuning** → Train/fine-tune LLaMA or similar models on Assamese-specific data for better performance.  

---

## 🏆 Conclusion
- This work demonstrates the feasibility of **LLMs in low-resource languages** like Assamese using **prompt engineering**.  
- Our analysis shows that **Zero-Shot prompting** can outperform Few-Shot and CoT in factual summarization tasks.  
- With improved prompting and fine-tuning, this approach can contribute significantly to **Assamese NLP research**.  

---

## 📚 References
- [ROUGE Metric](https://aclanthology.org/W04-1013/)  
- [BERTScore Paper](https://arxiv.org/abs/1904.09675)  
- [LLaMA Models](https://ai.meta.com/llama/)  
- [Kaggle Assamese Dataset - News18 & NENow](https://www.kaggle.com/datasets/krishnabhdas/assamese-news-article-dataset)

---
