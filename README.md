# Retrieval-Augmented Generation (RAG) System for PDF Question Answering

Welcome to the Retrieval-Augmented Generation (RAG) System project! This advanced system enables users to upload PDF documents and ask questions about their content. By combining document retrieval with powerful language generation models, it provides accurate, context-aware answers based on the uploaded files. 


## Key Features

### 1. Document Ingestion
- **PDF Loading:** Leverages `PyPDFium2Loader` for efficient and reliable PDF processing.
- **Text Splitting:** Segments PDF content into manageable chunks while retaining context:
  - **Semantic Chunking:** Breaks text into meaningful units to maintain readability and relevance.
  - **Recursive Splitting:** Further divides chunks to fit within token limits for language model processing.

### 2. Embeddings and Vector Store
- **Embeddings Generation:** Converts text chunks into dense semantic vectors using `FastEmbedEmbeddings`.
- **Vector Store:** Embeddings are stored in a `Qdrant` vector database, enabling fast and precise information retrieval.

### 3. Reranking and Filtering
- **Reranking:** Uses `FlashrankRerank` to prioritize document chunks based on their relevance to the query.
- **LLM Chain Filtering:** (Optional) Further refines results using a Large Language Model (LLM) for enhanced accuracy.

### 4. Question Answering (QA) Chain
- **Prompt Construction:** Builds structured prompts with a conversational template for generating clear, concise answers.
- **Response Generation:** Provides answers in markdown format using either:
  - **Local Models:** `ChatOllama`
  - **Remote Models:** `ChatGroq`

### 5. User Interaction
- **Console-Based Interface:** Users interact with the system through a simple command-line interface (CLI).
- **Conversation Management:** Maintains session history to enable context-aware, multi-turn conversations.

### 6. Session and Document Management
- **Session Handling:** Preserves user context across multiple queries.
- **Document Upload:** Supports uploading and processing multiple PDFs simultaneously.



## How It Works

1. **Upload PDF:** Users upload one or more PDF documents. The system processes these files, splitting them into smaller chunks and embedding the content into a vector store.
2. **Submit a Query:** Users ask questions about the uploaded documents. The system retrieves the most relevant chunks, reranks them, and applies optional filtering.
3. **Generate Answer:** Based on the retrieved content, the system generates an accurate, context-aware response.
4. **Review and Interact:** Users can review the answer, with references to the source documents provided for transparency.



## Getting Started

### Prerequisites
Ensure you have the following installed:
- Python 3.8+

### Installation
1. Clone the repository and navigate to the project directory:
   ```bash
   git clone https://github.com/msa23003/RagifyQ-A.git
   cd your-repo-name
   ```
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Usage
To launch the application, use the command-line interface:
```bash
python main.py
```
Once running, you can upload PDFs, ask questions, and explore the system’s features.



## Contributing
We welcome contributions to this project! Here’s how you can help:
- Fork the repository.
- Make your changes and ensure they align with the project’s goals.
- Submit a pull request for review.


## License
This project is licensed under the MIT License. See the `LICENSE` file for more details.


## Acknowledgements
This project was made possible thanks to the following technologies:
- **PyPDFium2Loader** for PDF processing
- **FastEmbedEmbeddings** for embedding generation
- **Qdrant** for vector storage
- **FlashrankRerank** for reranking results
- **ChatOllama** and **ChatGroq** for language model-based responses

Special thanks to the creators of these tools and models for their incredible contributions to the open-source community!
