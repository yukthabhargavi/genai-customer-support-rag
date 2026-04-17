# GenAI Customer Support Assistant (RAG)

## Overview
This project implements an intelligent customer support assistant using Retrieval-Augmented Generation (RAG). It combines semantic search with large language models to generate accurate, context-aware responses for user queries.

The system is designed to automate repetitive customer support interactions, improve response quality, and reduce latency in real-time applications.

---

## Features
- Retrieval-Augmented Generation (RAG) pipeline  
- FAISS-based semantic document search  
- LangChain-powered prompt orchestration  
- Multi-turn conversational memory support  
- Intent-based query routing  
- FastAPI backend for real-time responses  

---

## Tech Stack
- Python  
- LangChain  
- FAISS (Vector Database)  
- FastAPI  
- OpenAI API  

---

## Architecture
1. User sends query via API  
2. Query is classified based on intent  
3. Relevant documents retrieved using FAISS  
4. LLM generates contextual response  
5. Conversation memory stores interaction history  

---

## Project Structure
## Project Structure

```bash
genai-customer-support-rag/
│
├── src/
│   ├── api/
│   │   └── main.py
│   ├── rag_pipeline/
│   │   └── pipeline.py
│   ├── utils/
│   │   └── helpers.py
│
├── data/
├── requirements.txt
├── README.md
```

---


## Prerequisites
- Python 3.9+  
- OpenAI API Key (optional)  
- pip / virtualenv  

---

## Clone the Repository
```bash
git clone https://github.com/yukthabhargavi/genai-customer-support-rag.git
cd genai-customer-support-rag
Environment Setup

Create and activate a virtual environment:

python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
Install Dependencies
pip install -r requirements.txt
Run the Application
uvicorn src.api.main:app --reload
API Usage

Example endpoint:

GET /ask?query=What is the refund policy?

Response:

{
  "response": "Refund policy is valid for 7 days..."
}
Impact
Automated ~70% of repetitive customer queries
Reduced average response time by ~28%
Improved consistency in multi-turn conversations
Future Improvements
Streaming responses for better UX
Hybrid search (keyword + vector)
Monitoring and evaluation pipeline
Notes

This project is built using open-source frameworks and customized for a customer support use case, including API deployment, retrieval optimization, and conversational handling.


---



### 4️⃣ Configuration

Create a `.env` file with your settings:
```env
OPENAI_API_KEY=your_api_key_here  # Optional
LANGCHAIN_API_KEY=your_api_key_here # Optional
LANGCHAIN_TRACING_V2= true # Optional
LANGCHAIN_PROJECT=your_project_id_here # Optional

```

---

## 🚀 Usage

### Local Development

1. **Preprocess and Index Data**
```bash
python -m src.indexing.preprocess
```

2. **Start the API Server**
```bash
uvicorn src.main:app --reload
```

3. Access the API at `http://localhost:8000`

### Docker Deployment

1. **Build and Start Containers**
```bash
docker-compose up --build
```

2. Access the API at `http://localhost:8000`

---

## 📡 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/answer` | Submit question and get response |
| `GET` | `/health` | Check API health status |

Example request:
```json
{
  "question": "How do I return a damaged product?"
}
```

---

## 🔄 Workflow Process

The system follows this process for each query:

1. **Input Processing**
   - Question validation
   - Safety checks
   - Topic classification

2. **Context Retrieval**
   - Document search
   - Relevance scoring
   - Context selection

3. **Response Generation**
   - Answer formulation
   - Quality validation
   - Safety verificatio



<p align="center">
   <img src="assets\flow.png" width="150"/>
</p>

---

## 🤝 Contributing

We welcome contributions! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Make your changes
4. Commit (`git commit -am 'Add new feature'`)
5. Push (`git push origin feature/improvement`)
6. Create a Pull Request

---



## 🙏 Acknowledgments

- [LangChain](https://github.com/hwchase17/langchain) - LLM framework
- [LangGraph](https://github.com/hwchase17/langgraph) - Workflow orchestration
- [FastAPI](https://fastapi.tiangolo.com/) - API framework
- [FAISS](https://github.com/facebookresearch/faiss) - Vector similarity search
- [Ollama](https://ollama.ai/) - Local LLM support

---

## ⭐ Star This Repo!

If you find this project useful, please consider giving it a star! 🌟

---

## 📩 Contact

For questions or feedback, please open an issue in the repository.

---
