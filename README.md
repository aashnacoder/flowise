RAG Chatbot using Flowise

This project demonstrates a Retrieval-Augmented Generation (RAG) Chatbot** built using **Flowise**. The chatbot is capable of answering user queries based on a provided document (e.g., PDF) using embeddings and conversational memory.

---

 Features

-  Load and process documents (PDF, JSON, etc.)
-  Smart text chunking using Recursive Character Text Splitter
-  Semantic search using embeddings
-  In-memory vector database for fast retrieval
-  Conversational AI using Mistral LLM
- Context-aware responses using chat memory
- Retrieval-based answers with context grounding

---

##  Architecture Overview

The system follows a typical **RAG pipeline**:

```

Document → Text Splitter → Embeddings → Vector Store → Retriever → LLM → Answer

````

---

##  Chatflow Components

### 1.  File Loader
- Loads input documents (PDF, JSON, etc.)
- Supports per-page or per-file parsing

### 2.  Recursive Character Text Splitter
- Splits text into chunks
- Chunk Size: 1000
- Overlap: 200

### 3.  Google Gemini Embeddings
- Model: `gemini-embedding-001`
- Converts text chunks into vector embeddings

### 4.  In-Memory Vector Store
- Stores embeddings in memory
- Performs similarity search
- Retrieves top relevant chunks

### 5. Mistral AI Chat Model
- Model: `mistral-tiny`
- Temperature: 0.9
- Max Tokens: 500

### 6.  Buffer Memory
- Maintains chat history
- Enables contextual conversation

### 7.  Conversational Retrieval QA Chain
- Combines:
  - LLM (Mistral)
  - Retriever (Vector Store)
  - Memory (Buffer Memory)
- Rephrases follow-up questions
- Generates context-based answers

---

##  How It Works

1. Upload a document (PDF recommended)
2. Text is split into smaller chunks
3. Each chunk is converted into embeddings
4. Embeddings are stored in a vector database
5. User asks a question
6. Relevant chunks are retrieved
7. LLM generates an answer using retrieved context
8. Chat history is maintained for follow-up queries

---

## Tech Stack

- **Flowise AI**
- **Google Generative AI (Gemini Embeddings)**
- **Mistral AI (LLM)**
- **Vector Store (In-Memory)**
- **LangChain Components (via Flowise)**

---

##  Setup Instructions

### 1. Install Flowise
```bash
npm install -g flowise
flowise start
````

### 2. Import Chatflow

* Open Flowise UI
* Click on **Import Chatflow**
* Upload the provided JSON file

### 3. Configure API Keys

* Add credentials for:

  * Google Generative AI (Gemini)
  * Mistral AI

### 4. Upload Document

* Use the File Loader node
* Upload your PDF or document

### 5. Run Chatbot

* Start asking questions based on your document

---

##  Example Use Case

* AI Ethics document Q&A
* Research paper assistant
* Internal knowledge base chatbot
* Educational assistant

---

##  Limitations

* In-memory vector store (data is not persistent)
* Performance depends on chunking and embeddings
* Requires API keys for external services

---

##  Future Improvements

* Add persistent vector database (Pinecone, FAISS, etc.)
* Improve prompt engineering
* Add citation-based responses
* Deploy as web app or API

---

##  Acknowledgements

* Flowise
* LangChain
* Google Generative AI
* Mistral AI

---

##  Contact

For queries or improvements, feel free to contribute or raise an issue!

<img width="1697" height="683" alt="Screenshot 2026-04-07 142011" src="https://github.com/user-attachments/assets/a6d6affd-5ca8-4916-85e0-dbd502a96f9b" />
<img width="576" height="697" alt="Screenshot 2026-04-07 142034" src="https://github.com/user-attachments/assets/4e244ab2-8aca-4ad4-9c54-f8ff72c6c8eb" />
<img width="532" height="717" alt="Screenshot 2026-04-07 142108" src="https://github.com/user-attachments/assets/9dbde062-aa7c-4d2b-89e6-992f7fcb0917" />
<img width="498" height="683" alt="Screenshot 2026-04-07 142811" src="https://github.com/user-attachments/assets/d3b32316-4d9d-4008-8044-7a54566d3bb2" />
<img width="503" height="691" alt="Screenshot 2026-04-07 142920" src="https://github.com/user-attachments/assets/a727a927-d8c3-4ebf-8605-16f56f94a56a" />

