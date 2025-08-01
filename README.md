# 🧠 Smart Recycling Assistant

This project integrates image classification, text classification, and retrieval-augmented generation (RAG) to build an intelligent assistant 
that suggests recycling instructions based on either a waste image or a textual description.

---

## 📌 Features

* 🖼️ **Image-Based Waste Classification** using CNN.
* 📝 **Text-Based Waste Classification** using ALBERT (Transformer model).
* 🔎 **Recycling Policy Retrieval** using semantic search with Sentence Transformers.
* 🧾 **Instruction Generation** using FLAN-T5 language model.

---

## 📁 Project Structure

```
├── realwaste_data/                     # RealWaste dataset (images)
│   └── realwaste-main/RealWaste/      # 9 waste categories
├── waste_descriptions.csv             # Text-based descriptions (classification)
├── waste_policy_documents.json        # Reference policy documents (for RAG)
├── notebook.ipynb                     # Main notebook (all steps)
├── README.md                          # Project documentation
```

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/recycling-assistant.git
cd recycling-assistant
```

### 2. Required packages include:

* `transformers`
* `sentence-transformers`
* `tensorflow`
* `torch`
* `scikit-learn`
* `nltk`
* `pandas`, `matplotlib`, `seaborn`

### 3. Mount Drive (Colab Only)

```python
from google.colab import drive
drive.mount('/content/drive')
```

---

## 🔄 How It Works

### ➤ Input Types:

* An **image** (e.g., photo of a soda can)
* A **text** description (e.g., `"crushed soda can"`)

### ➤ Output:

* Predicted **waste category**
* **Confidence** score
* Policy-aligned **recycling instructions**
* Relevant **policy document chunks**

### ➤ Sample Usage

```python
result = waste_management_assistant("realwaste_data/RealWaste/Cardboard/Cardboard_205.jpg", input_type="image")

# Output
{
  "category": "Cardboard",
  "confidence": 0.99,
  "instructions": "Flatten and place in recycling bins...",
  "relevant_policy_chunks": [...]
}
```

---

## 🧪 Models Used

| Task                 | Model                     | Notes                        |
| -------------------- | ------------------------- | ---------------------------- |
| Image Classification | CNN                       | Trained on RealWaste         |
| Text Classification  | ALBERT (`albert-base-v2`) | Lightweight transformer      |
| Embedding Generator  | `all-MiniLM-L6-v2`        | Fast SentenceTransformer     |
| Text Generator       | `flan-t5-small`           | Instruction-tuned generation |

---

## 📊 Evaluation Criteria

* ✅ **Accuracy** of classification
* ✅ **Relevance** of generated recycling instructions
* ✅ **Clarity & Specificity** of output
* ✅ **Policy Coverage** and compliance

---

## 🧠 Authors

Alejandro Silva
---

## 📜 License

This project is for academic and learning purposes only.
