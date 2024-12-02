# Website Bot Using Llama 2, Pinecone, & LangChain

## Overview

This project demonstrates how to build a website bot capable of retrieving and answering questions based on the content of provided URLs. The solution leverages:
- **Llama 2** as the language model,
- **Pinecone** for vector storage,
- **LangChain** for handling document processing and retrieval.

The bot processes website content, converts it into embeddings, and uses a RetrievalQA chain to answer user queries.

---

## Features

- **Website Content Retrieval**: Fetches and processes data from URLs.
- **Text Chunking**: Splits large text content into manageable chunks.
- **Embeddings Generation**: Converts text chunks into dense vector embeddings.
- **Knowledge Base Creation**: Stores embeddings in Pinecone for efficient similarity search.
- **Custom LLM**: Uses a Hugging Face pipeline to wrap the Llama 2 model for custom predictions.
- **Retrieval QA**: Provides accurate answers to user queries with source references.

---

## Setup

### 1. Clone the Repository
```bash
git clone <repository-url>
cd <repository-name>
```

### 2. Install Dependencies

Ensure you have Python 3.8+ installed. Install the required packages:
```bash
pip install -r requirements.txt
```

### 3. Configure API Keys

Set up environment variables for Pinecone:
```bash
export PINECONE_API_KEY="your_pinecone_api_key"
export PINECONE_API_ENV="your_pinecone_environment"
```

If you're using Hugging Face, ensure you have an access token:
```bash
export HUGGINGFACEHUB_API_TOKEN="your_huggingface_api_token"
```

---

## Usage

### Run the Notebook

1. Open the notebook `Website_bot_using_Llama2,_Pinecone_&_LangChain.ipynb`.
2. Follow the steps in the notebook to:
   - Retrieve website content.
   - Split the text into chunks.
   - Generate embeddings and create a Pinecone index.
   - Set up and test the RetrievalQA chain.

### Interactive Bot
Run the provided loop in the notebook to interact with the bot:
```python
while True:
  user_input = input("Input Prompt: ")
  if user_input.lower() == 'exit':
    print("Exiting...")
    break
  result = qa.run(user_input)
  print(f"Answer: {result}")
```

---

## Components

### 1. Libraries
- **LangChain**: Manages the document pipeline and QA chain.
- **Pinecone**: Stores and retrieves vector embeddings.
- **Hugging Face Transformers**: Provides pre-trained models and pipelines.
- **Llama 2**: Fine-tuned language model for predictions.

### 2. Workflow
- **Step 1**: Retrieve and preprocess content from URLs.
- **Step 2**: Convert text into dense vector embeddings using Hugging Face models.
- **Step 3**: Store embeddings in Pinecone.
- **Step 4**: Use LangChain's RetrievalQA to answer queries.

---

## Examples

### Query Example
**Question**: "How does Llama 2 outperform other models?"

**Answer**: Llama 2 models outperform their predecessors and competitors by leveraging advanced pretraining techniques, enhanced data cleaning, and training on 2 trillion tokens.

---

## Contributing

Contributions are welcome! Please fork the repository, make changes, and submit a pull request.

---

## License

This project is open-source under the MIT License. See `LICENSE` for details.
