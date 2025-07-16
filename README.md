# 📈 Sentiment Analysis Using Neural Networks

🧠 Overview:
This project performs sentiment classification on financial sentences into:
- 😠 Negative (0)
- 😐 Neutral (1)
- 🙂 Positive (2)

We built and evaluated multiple neural network models using pretrained Word2Vec embeddings. The aim is to find the best model that handles imbalanced classes while delivering accurate predictions.

📊 Dataset:
- 📁 5,842 short financial sentences
- 🏷️ Labels: 0 (negative), 1 (neutral), 2 (positive)
- 🧹 Preprocessing: replaced numeric tokens (e.g., "USD7m" → "7 million USD"), standardized financial suffixes (k, m, b, t), cleaned text

⚙️ Steps:

1️⃣ Preprocessing:
- Replaced numerics and standardized suffixes
- Removed special characters
- Kept stopwords and casing (important for sentiment)
- Skipped lemmatization

2️⃣ Embedding Matrix:
- 💾 Used pretrained Word2Vec (Google News 300)
- 🔤 Tokenized and indexed words using Keras
- 🧱 Constructed reduced embedding matrix
- 🧮 Labels converted to one-hot vectors

3️⃣ Models Trained:

🔸 Model 1: FFN + Frozen Embeddings
- ✅ Accuracy: 64%
- ⚠️ Weak on negative class

🔸 Model 2: FFN + Fine-tuned Embeddings
- ✅ Accuracy: 67%
- 📈 Better F1 for positives

🔸 Model 3: Stacked LSTM (Frozen)
- ✅ Accuracy: 75%
- 🎯 Balanced and strong

🔸 Model 4: Bi-directional SimpleRNN
- ✅ Accuracy: 69%
- ❌ Underperformed on negatives

🔸 Model 5: Deep LSTM (3 layers)
- ✅ Accuracy: 73%
- 🧩 More complex, moderate gain

🔸 Model 6: Stacked Bi-LSTM (Frozen)
- ✅ Accuracy: 74%
- 🏆 Best F1 + fewer parameters

🔸 Model 7: Bi-LSTM (Fine-tuned)
- ⚠️ High overfitting risk
- ❌ No clear improvement

🏁 Conclusion:
🥇 **Model 6** (Stacked Bi-LSTM with frozen embeddings) gave the best overall results. It balanced precision, recall, and complexity—making it suitable for real-world deployment.

📦 Files Included:
- 📄 problem.pdf – Project prompt
- 📓 coded_sol.ipynb – All model code
- 🧾 report.pdf – In-depth explanation and evaluation
- 📊 data.csv – Cleaned, labeled financial text

🚀 How to Run:
Install required packages:
