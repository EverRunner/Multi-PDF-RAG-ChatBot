# RAG-based PDF Chat Application

A Streamlit-based application that allows users to chat with their PDF documents using RAG (Retrieval-Augmented Generation) and OpenAI's GPT model.

## Features

- 📄 Upload multiple PDF files
- 💬 Ask questions about the content of your PDFs
- 🔍 Intelligent text chunking and vector search
- 🤖 AI-powered responses using OpenAI's GPT-3.5
- 📊 User-friendly Streamlit interface

## Prerequisites

Before running the application, make sure you have Python installed and the following dependencies:

```bash
pip install streamlit
pip install openai
pip install chromadb
pip install tiktoken
pip install PyPDF2
pip install faiss-cpu
pip install langchain
pip install langchain-openai
pip install langchain-anthropic
pip install spacy
python -m spacy download en_core_web_sm
pip install python-dotenv
```

## Environment Setup

1. Create a `.env` file in your project root directory
2. Add your OpenAI API key:

```
OPENAI_API_KEY=your_api_key_here
```

## How to Run

1. Clone this repository:

```bash
git clone https://github.com/EverRunner/Multi-PDF-RAG-ChatBot.git
cd Multi-PDF-RAG-ChatBot
```

2. Install the required packages:

```bash
pip install -r requirements.txt
```

3. Run the Streamlit app:

```bash
streamlit run app.py
```

## Usage Guide

1. **Starting the Application**

   - Launch the application using `streamlit run app.py`
   - The application will open in your default web browser

2. **Uploading PDFs**

   - Use the sidebar to upload one or more PDF files
   - Click the "Submit & Process" button to analyze the documents

3. **Asking Questions**
   - Type your questions in the text input field
   - The AI will respond based on the content of your uploaded PDFs

## How It Works

1. **PDF Processing**

   - Extracts text from uploaded PDF files using PyPDF2
   - Processes multiple PDFs simultaneously

2. **Text Processing**

   - Splits extracted text into manageable chunks using RecursiveCharacterTextSplitter
   - Chunk size: 1000 characters with 200 character overlap

3. **Vector Embedding**

   - Converts text chunks into vector embeddings using SpaCy
   - Stores embeddings in FAISS for efficient similarity search

4. **Question Answering**
   - Uses OpenAI's GPT-3.5 model for generating responses
   - Implements RAG (Retrieval-Augmented Generation) for accurate answers
   - Retrieves relevant context from the vector store

## Technical Components

- **Frontend Framework**: Streamlit
- **PDF Processing**: PyPDF2
- **Text Processing**: LangChain
- **Embeddings**: SpaCy
- **Vector Store**: FAISS
- **LLM Integration**: OpenAI GPT-3.5
- **RAG Implementation**: LangChain + FAISS

## Limitations

- Requires an active internet connection
- Processing large PDF files may take time
- Requires a valid OpenAI API key
- Response quality depends on PDF content clarity
- Maximum token limits apply based on the OpenAI model used

## Best Practices

1. **PDF Preparation**

   - Use clear, well-formatted PDFs
   - Ensure PDFs are text-searchable
   - Keep individual PDF sizes manageable

2. **Querying**
   - Ask clear, specific questions
   - Reference specific sections when possible
   - Break down complex questions into simpler ones

## Troubleshooting

Common issues and solutions:

1. **API Key Issues**

   - Ensure your OpenAI API key is correctly set in the .env file
   - Check API key permissions and usage limits

2. **PDF Processing Errors**

   - Verify PDF is not corrupted
   - Ensure PDF is text-based, not scanned images
   - Check PDF file permissions

3. **Memory Issues**
   - Reduce chunk size for large documents
   - Process fewer PDFs simultaneously
   - Ensure sufficient system resources

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/improvement`)
3. Make your changes
4. Commit your changes (`git commit -am 'Add new feature'`)
5. Push to the branch (`git push origin feature/improvement`)
6. Create a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- OpenAI for GPT-3.5
- Streamlit team for the amazing framework
- LangChain community for RAG implementation tools
- FAISS team for vector similarity search capabilities

## Contact

For questions and support, please open an issue in the GitHub repository.
