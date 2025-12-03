## 📌 Prompting

Prompting means writing **clear, detailed, and structured instructions** so that an LLM can understand what you want and produce a **specific**, accurate response.

### Why Prompts Matter
A well-written prompt improves:
- Context understanding  
- Output accuracy  
- Formatting consistency  
- Model behavior control
  
### ✔️ Example
**Bad Prompt:** 

"Explain AI."

**Good Prompt:**

"Explain Artificial Intelligence in simple terms.
Include:

- A brief 2–3 sentence definition
- Three real-world examples
- Key benefits and limitations
- Format the output using bullet points."


 ✔️ Good prompts = better LLM performance.

⭐ **Prompting is often a “trial and error” process — you adjust your prompt until the model consistently outputs what you want.**

---

## 📌 RAG (Retrieval Augmented Generation)

RAG is used when an LLM needs **external knowledge** that it was not originally trained on.

### How RAG Works
1. User enters a query  
2. Query is converted into a **vector embedding**  
3. A **vector similarity search** runs on a vector database  
4. The most relevant context is retrieved  
5. The context + the user prompt are combined  
6. The LLM generates a more accurate and grounded response  

### ✔️ Example of RAG Flow

**User Query:**  
> "Explain the refund policy of Company X."

**Process:**  
- Query → embedding → vector search  
- Finds refund policy from uploaded documents  
- LLM uses the retrieved text to craft an accurate answer  

Without RAG, the model may hallucinate.  
With RAG, the model uses **real data**, not assumptions.

---

### 🧩 Types of RAG

- **Adaptive RAG**  
  The system decides dynamically what type of retrieval or reasoning is needed.

- **Agentic RAG**  
  Agents perform retrieval, validation, planning, or multistep reasoning.

- **Corrective RAG**  
  A second retrieval or validation step corrects hallucinations or mistakes.

---

## 📌 Fine-Tuning

Fine-tuning means taking a **pretrained LLM** and training it further on **your custom data** so it becomes specialized for a task.

### When to Use Fine-Tuning
- You need domain-specific reasoning  
- The model should follow strict response formats  
- You want behavior that prompting cannot achieve  

### ✔️ Example Scenario

Suppose you have:
- 10,000 medical diagnosis Q&A pairs  
- And you want the model to answer like a medical expert  

You can **fine-tune** a pretrained model so it learns:
- Domain vocabulary  
- Consistent medical reasoning  
- Preferred answer format  

During fine-tuning, **model weights are updated**, unlike RAG or prompting.

---

## ⚠️ Challenges & Costs

### Fine-Tuning Challenges
- **High training cost** (GPU hours are expensive)  
- **Data preparation cost** (cleaning, labeling, formatting)  
- Requires ML expertise  
- Risk of overfitting  
- Must maintain model versions  

---

### RAG Challenges & Costs
- Cost of storing vectors in a database  
- Cost of frequent vector searches  
- Maintaining embeddings, updating knowledge  
- Requires infrastructure (e.g., Pinecone, Chroma, Weaviate)

RAG reduces hallucinations but needs good:
- Chunking  
- Embedding models  
- Retrieval strategy  

---

### Prompting Challenges
- Requires experimentation (“hit and trial”)  
- Only uses the capabilities of the **existing pretrained model**  
- No ability to learn new information  
- Prompt complexity can grow quickly  

Prompting works best when you want to **explore the model’s built-in capabilities** rather than teach it new knowledge.

---

## 📌 Summary Table

| Method | What It Does | When to Use | Cost | Pros | Cons |
|-------|--------------|-------------|------|------|------|
| **Prompting** | Give instructions to the model | Simple tasks / formatting | ⭐ Low | Fast, no training needed | Limited to existing model knowledge |
| **RAG** | Retrieves external data to improve answers | Knowledge-based apps | ⭐⭐ Medium | Reduces hallucinations, dynamic | Needs vector DB + infra |
| **Fine-Tuning** | Train model on custom data | Domain-specific tasks | ⭐⭐⭐ High | Highly accurate | Expensive + complex |
