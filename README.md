# 📚 AI-Powered Research Paper Q&A System

A scalable microservice-based RAG system that enables multi-document upload, semantic retrieval, and LLM-powered question answering for research papers.

---

## 🧱 Project Architecture

rag-research-qa/ ├── services/ │ ├── upload_service/ # Handles PDF parsing and embedding │ ├── question_service/ # Processes questions, performs retrieval + LLM │ └── shared/ # Common utils and shared modules ├── vector_store/ # FAISS or Qdrant integration ├── k8s/ # K8s manifests (YAMLs) ├── helm/ # Helm chart for full deployment ├── .github/ # CI/CD (GitHub Actions) ├── docs/ # Architecture & API specs ├── docker-compose.yml # Local dev (optional) └── README.md

yaml
Copy
Edit

---

## 🔧 Tech Stack

| Layer       | Tools                                        |
|-------------|-----------------------------------------------|
| Backend     | FastAPI (async), Redis, PyMuPDF, LangChain    |
| Embeddings  | OpenAI / BGE / HuggingFace Transformers       |
| Vector DB   | FAISS / Qdrant                                |
| LLM         | GPT-3.5 / Claude / Local Model (optional)     |
| CI/CD       | GitHub Actions + Docker                       |
| Deployment  | Kubernetes + Helm                             |
| Monitoring  | Prometheus + Grafana (via ServiceMonitor)     |

---

## 🎯 Features

- [x] Upload PDF files and split into text chunks
- [x] Embed chunks into a vector DB
- [x] Ask natural language questions
- [x] Retrieve relevant chunks (Top-K)
- [x] Answer with LLM (RAG pipeline)
- [x] Cache results to Redis
- [x] CI/CD with automated tests
- [x] Helm chart & K8s ready

---

## 🚀 Quick Start (Local Dev)

```bash
# 1. Start Redis and FAISS/Qdrant (via docker-compose)
docker-compose up -d

# 2. Run upload service
cd services/upload_service && uvicorn app.main:app --reload

# 3. Run question service
cd services/question_service && uvicorn app.main:app --reload
📁 Docs
docs/architecture.md: System architecture

docs/api_spec.md: API endpoints, parameters, and response format

k8s/: Kubernetes manifests (deployment, service, ingress)

helm/: Helm chart for scalable deployment

🧑‍💻 Author
Built by Ling Duan — For backend/RAG engineering, AI Infra, and DevOps showcase.

📬 Contact
If you're a researcher, engineer, or team interested in AI-assisted document Q&A — feel free to connect!
