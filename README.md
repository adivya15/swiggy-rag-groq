# 📊 RAG-based Question Answering System  
## Swiggy Annual Report FY 2023–24

---

## 🎯 Objective

Build a Retrieval-Augmented Generation (RAG) system that answers user questions strictly using the Swiggy Annual Report FY 2023–24.

The system:
- Prevents hallucination
- Uses semantic retrieval
- Generates grounded responses
- Provides an interactive Gradio interface

---

## 📄 Dataset

- **Document:** Swiggy Annual Report FY 2023–24
- **Format:** PDF
- **Source:** Official Swiggy Investor Relations Website  
  (https://www.swiggy.com/investor-relations)

---

## 🏗️ System Architecture

User Query  
→ SentenceTransformer Embedding  
→ FAISS Vector Search  
→ Top-K Relevant Chunks  
→ Groq LLM (LLaMA 3)  
→ Final Grounded Answer  

---

## ⚙️ Tech Stack

- **Embedding Model:** all-MiniLM-L6-v2
- **Vector Database:** FAISS
- **LLM:** Groq (llama-3.1-8b-instant)
- **UI:** Gradio
- **Environment:** Google Colab

---

## 🔄 Pipeline Explanation

### 1️⃣ Document Processing
- PDF loaded
- Cleaned and chunked
- Overlapping chunks used for financial continuity

### 2️⃣ Embedding & Indexing
- Text converted into dense embeddings
- Stored in FAISS vector database

### 3️⃣ Retrieval-Augmented Generation
- Top-K relevant chunks retrieved
- Strict anti-hallucination prompt enforced
- Groq LLM generates context-grounded answer

### 4️⃣ Hallucination Prevention
- Temperature = 0
- Strict grounding instructions
- Explicit fallback message:
I could not find this information in the Swiggy Annual Report.
---

## 🌐 Live Demo (Gradio)

The system includes a Gradio interface for interactive question answering.

👉 **Live Demo Link:**  
(https://d5a850714d69256b82.gradio.live)

Users can:
- Enter natural language questions
- View generated answers
- Inspect supporting context

---

## 💬 Example Queries

- What was the net loss for FY24?
- Who is the Managing Director & Group CEO?
- How many board meetings were held?
- What was total income in FY24?

---

## 🚀 How to Run Locally

1. Install dependencies:
 ```
pip install -r requirements.txt
```
   
2. Add your Groq API key:
 ```
export GROQ_API_KEY=your_key
```

3. Run notebook or script.

4. Launch Gradio UI

    A public link will be generated.

---

## 📊 Strengths

- Fully grounded RAG pipeline
- No hallucination policy
- Fast inference via Groq
- Interactive UI using Gradio
- Clean modular implementation

---

## ⚠️ Limitations

- Retrieval quality depends on chunking strategy
- No hybrid (BM25 + Vector) search implemented
- No reranking stage

---

## 👤 Author

Divya Addagatla
