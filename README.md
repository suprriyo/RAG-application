# RAG-Based Question Answering System

A Retrieval-Augmented Generation (RAG) system for educational content that allows students to upload PDF textbooks and ask questions about their content.



## Features

-  **PDF Upload**: Upload educational PDFs (textbooks, papers, etc.)
-  **Interactive Chat**: Ask questions and get answers based on uploaded content
-  **Source Citations**: View which parts of the documents were used to generate answers
-  **Multi-Document Support**: Upload multiple PDFs and query across all documents
-  **Performance Metrics**: See answer generation time
-  **Document Management**: View uploaded documents and manage the database


## Usage Guide

### Uploading Documents

1. Go to the "Upload Documents" tab
2. Click "Choose a PDF file" and select your document
3. Click "Process Document"
4. Wait for processing to complete (you'll see progress updates)

### Asking Questions

1. Go to the "Chat" tab
2. Type your question in the chat input
3. Press Enter or click Send
4. View the answer along with source citations
5. Click "View Sources" to see which parts of the document were used

### Managing Documents

- View uploaded documents in the sidebar
- See document statistics (chunks, size, upload time)
- Clear conversation history with "Clear Conversation" button
- Reset entire database with "Reset Database" button

## Configuration

Edit `config.yaml` to customize:

- **Embedding Model**: Choose between OpenAI or HuggingFace embeddings
- **LLM Provider**: Use OpenAI GPT or Anthropic Claude
- **Chunk Size**: Adjust text chunking parameters
- **Retrieval Settings**: Configure how many relevant chunks to retrieve

Example configuration:

```yaml
embedding:
  provider: "openai"
  model: "text-embedding-ada-002"

llm:
  provider: "openai"
  model: "gpt-3.5-turbo"
  temperature: 0.7
  max_tokens: 500

chunking:
  chunk_size: 1000
  chunk_overlap: 200

retrieval:
  top_k: 4
  score_threshold: 0.7  # Rank all document chunks by similarity score,Keep only chunks where similarity ≥ 0.7. Pass those to the LLM as context for answer generation. 
```


## Technology Stack

- **Framework**: LangChain (Python)
- **Vector Database**: ChromaDB
- **Embeddings**: OpenAI / HuggingFace
- **LLM**: OpenAI GPT / Anthropic Claude
- **PDF Processing**: PyPDF2
- **Web Interface**: Streamlit
- **CLI**: Click






##  Contributing

Contributions are welcome! Please feel free to submit a Pull Request.





##  Acknowledgments

- Built with [Streamlit](https://streamlit.io)
- Powered by [LangChain](https://langchain.com)
- Vector storage by [ChromaDB](https://www.trychroma.com)
- LLM by [OpenAI](https://openai.com)


