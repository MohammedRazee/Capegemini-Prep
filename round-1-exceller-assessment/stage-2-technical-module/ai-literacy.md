# AI Literacy Cheat Sheet

[← Back to Stage 2](README.md)

> 20 of your 40 technical MCQs are on AI. Learn the terms below and you'll be able to answer most of them.

---

## 1. AI foundations & Generative AI

| Term | Plain-English meaning |
|---|---|
| **AI → ML → Deep Learning → GenAI** | Nested circles. AI is the broad goal. ML learns from data. Deep learning uses neural networks. **Generative AI** creates new content (text, images, code). |
| **Foundation model** | A huge model trained on broad data that can be adapted to many tasks (e.g., GPT, Claude, Gemini, Llama). |
| **LLM (Large Language Model)** | A foundation model for text. It predicts the **next token** based on everything before it. |
| **Token** | A chunk of text (roughly ¾ of a word in English). Models read, write and are priced in tokens. |
| **Context window** | The maximum number of tokens the model can "see" at once (your prompt + its answer). Anything beyond that is forgotten. |
| **Training vs inference** | *Training* is learning from data (expensive, done once). *Inference* is using the trained model to answer (every time you chat). |
| **Parameters** | The learned numbers inside the model. More parameters generally means a more capable model, but also a more expensive one. |
| **Temperature** | Randomness setting. **Low (0–0.3)** gives focused, consistent output, good for code and facts. **High (0.8+)** gives creative, varied output. |
| **Hallucination** | The model confidently states something **false or made up**. The biggest limitation of LLMs. |
| **Knowledge cutoff** | The date the training data ends. The model doesn't know events after it unless given tools or documents. |
| **Multimodal** | Can handle more than text: images, audio, video. |
| **Fine-tuning** | Further training a model on your own data to specialise it. |

**Capabilities:** summarising, drafting, translating, explaining, generating and reviewing code, classifying, extracting data.
**Limitations:** hallucinations, outdated knowledge, inconsistent maths, bias from training data, no real understanding or intent, privacy risk if you paste sensitive data.

---

## 2. Prompt engineering & AI productivity

| Concept | Meaning |
|---|---|
| **Prompt** | The input/instructions you give the model. |
| **System prompt** | Hidden instructions that set the model's role and rules for the whole conversation. |
| **Zero-shot** | Asking with no examples. |
| **Few-shot** | Giving 2–3 examples of input → output so the model copies the pattern. |
| **Chain-of-thought** | Asking the model to reason step by step before answering. Improves logic and maths. |
| **Role prompting** | "You are a senior Java developer…" sets expertise and tone. |
| **Context setting** | Giving the background the model needs: audience, constraints, data, goal. |
| **Delimiters** | Separating instructions from data with tags or quotes, e.g. `"""text"""` or `<data>…</data>`. |
| **Iterative prompting** | Refining your prompt based on the output. Prompting is a conversation, not one shot. |
| **GitHub Copilot** | An AI pair programmer inside the code editor. Suggests code as you type, and can chat about and explain code. |

**A good prompt has:** Role · Task · Context · Constraints · Output format · (Examples)

```
❌ "write code for sorting"
✅ "You are a Java tutor. Write a Java method that sorts an int array in ascending
   order using merge sort. Input size up to 10^5. Return the sorted array.
   Add comments explaining each step and state the time complexity."
```

---

## 3. Advanced AI systems

| Concept | Meaning |
|---|---|
| **RAG (Retrieval-Augmented Generation)** | Before answering, the system **retrieves** relevant documents (e.g., company policies) and adds them to the prompt. Reduces hallucination and gives up-to-date or private knowledge **without retraining**. |
| **Embeddings** | Numbers (vectors) that represent the *meaning* of text. Similar meanings give vectors that are close together. |
| **Vector database** | Stores embeddings so the system can find "the most similar documents" fast (e.g., Pinecone, FAISS, Chroma). |
| **RAG pipeline** | Documents → split into chunks → embed → store in a vector DB → user question → embed → retrieve top matches → add to prompt → LLM answers using them. |
| **AI agent** | An LLM that can **decide actions and use tools** (search, run code, call APIs) in a loop to reach a goal. |
| **Agent loop** | **Think → Act (use a tool) → Observe the result → repeat** until done. |
| **Agentic AI** | Systems where AI plans and carries out multi-step tasks with some autonomy, not just single replies. |
| **Tool use / function calling** | The model outputs a structured request (e.g., `get_weather("Bengaluru")`) that your code executes. |
| **Multi-step workflow** | Chaining steps: e.g., extract → summarise → translate → email. Each step's output feeds the next. |
| **RAG vs fine-tuning** | RAG = *give it the knowledge at question time* (cheap, easy to update). Fine-tuning = *change the model itself* (costly; for style or specialised behaviour). |

---

## 4. Responsible AI & evaluation

| Concept | Meaning |
|---|---|
| **Output validation** | Never trust AI output blindly. Check facts, test code and verify sources. |
| **Human-in-the-loop** | A human reviews or approves AI decisions, especially high-stakes ones. |
| **Bias** | Unfair patterns from training data (e.g., gender bias in hiring suggestions). Detect it with diverse test cases. |
| **Responsible AI principles** | **Fairness, transparency, accountability, privacy & security, reliability & safety, inclusiveness.** |
| **Data privacy** | Don't paste confidential client data, passwords or personal data into public AI tools. |
| **Explainability** | Being able to explain *why* the AI produced an output. |
| **Grounding** | Tying answers to trusted sources (e.g., via RAG) and citing them. |
| **Evaluation** | Measuring AI quality: accuracy, relevance, consistency, safety, and test cases with known answers. |
| **Deepfakes / misuse** | AI-generated fake media; one reason for watermarking and usage policies. |

> 💡 **Exam rule of thumb:** when an option says AI is *always* right, needs *no* review, or should be used with *confidential data freely*, it's wrong.

---

## 🧪 15 practice MCQs

Answers are at the bottom. Cover them and try first.

1. An LLM generates text by:
   a) Searching the internet for each answer b) Predicting the next token based on previous tokens c) Copying from a fixed database d) Running SQL queries
2. A model states a fake research paper title with full confidence. This is called:
   a) Overfitting b) Hallucination c) Tokenization d) Fine-tuning
3. For generating consistent, accurate code, the best temperature is:
   a) Low (≈0–0.2) b) High (≈1.0) c) Temperature doesn't matter d) Negative
4. A company wants its chatbot to answer from its latest HR policy PDFs without retraining the model. Best approach:
   a) Fine-tuning b) RAG c) Increase temperature d) Use a bigger model
5. In RAG, what is stored in the vector database?
   a) Raw passwords b) Embeddings of document chunks c) Model parameters d) User IP addresses
6. Giving the model two worked examples before your question is:
   a) Zero-shot b) Few-shot c) Chain-of-thought d) Fine-tuning
7. "Explain your reasoning step by step before giving the final answer" is an example of:
   a) Chain-of-thought prompting b) Role prompting c) RAG d) Embedding
8. Which is the BEST prompt?
   a) "fix code" b) "make it better" c) "You are a Java reviewer. Find the bug in the code below that causes an ArrayIndexOutOfBoundsException, explain it, and give the corrected method." d) "code???"
9. An AI agent differs from a basic chatbot because it:
   a) Always uses a higher temperature b) Can plan and take actions using tools in a loop c) Has no context window d) Cannot use APIs
10. The context window refers to:
    a) The screen size of the chat app b) The maximum tokens the model can process at once c) The number of users d) The training dataset
11. GitHub Copilot is primarily:
    a) A version control system b) An AI pair programmer that suggests code in the editor c) A cloud database d) A CI/CD tool
12. Before deploying AI-generated code to production, you should:
    a) Deploy immediately, AI code is tested b) Review, test and validate it c) Ask the AI if it's correct and trust the answer d) Remove all comments
13. Which is NOT a responsible AI principle?
    a) Fairness b) Transparency c) Accountability d) Maximum automation without human review
14. Pasting a client's confidential source code into a public AI chatbot is mainly a risk to:
    a) Model speed b) Data privacy and security c) Token cost d) Temperature
15. An AI resume screener rejects more female candidates for technical roles. This is an example of:
    a) Hallucination b) Bias c) Grounding d) Low latency

<details>
<summary><b>Show answers</b></summary>

1-b · 2-b · 3-a · 4-b · 5-b · 6-b · 7-a · 8-c · 9-b · 10-b · 11-b · 12-b · 13-d · 14-b · 15-b

</details>
