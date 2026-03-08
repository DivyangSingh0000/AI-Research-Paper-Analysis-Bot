# AI Research Paper Analysis Chat Bot

## Introduction
------------
A multi-tool AI agent that researches topics, reads articles, summarizes findings, and saves notes – all through a simple API. Built to demonstrate tool use, multi-step reasoning, and memory in LLM agents.

## How It Works
------------
The application follows these steps to provide responses to your questions:

1. PDF Loading: The app reads multiple PDF documents and extracts their text content.

2. Text Chunking: The extracted text is divided into smaller chunks that can be processed effectively.

3. Language Model: The application utilizes a language model to generate vector representations (embeddings) of the text chunks.

4. Similarity Matching: When you ask a question, the app compares it with the text chunks and identifies the most semantically similar ones.

5. Response Generation: The selected chunks are passed to the language model, which generates a response based on the relevant content of the PDFs.

## Dependencies and Installation
----------------------------
To install the AI Research Paper Analysis Chat Bot, please follow these steps:

1. Clone the repository to your local machine.

2. Install the required dependencies by running the following command:
   ```
   pip install -r requirements.txt
   ```

3. Obtain an API key from Groq and add it to the `.env` file in the project directory.
```commandline
GROQ_API_KEY=your_secrit_api_key
```

## Architecture
------------
```
┌─────────────┐       ┌─────────────────────────────────────┐
│   Client    │ ───▶ │           FastAPI Server             │
└─────────────┘       │                                     │
                      └───────────────┬─────────────────────┘
                                     │
                              ┌──────▼──────┐
                              │  LangChain  │
                              │             │
                              └──────┬──────┘
                                     │
          ┌──────────────────────────┼──────────────────────────┐
          ▼                          ▼                          ▼
┌─────────────────┐      ┌─────────────────────┐      ┌─────────────────┐
│  Web Search     │      │   Web Scraper       │      │   Memory Store  │
│                 │      │                     │      │                 │
└─────────────────┘      └─────────────────────┘      └─────────────────┘
```

## Usage
-----
To use the AI Research Paper Analysis Chat Bot, follow these steps:

1. Ensure that you have installed the required dependencies and added the OpenAI API key to the `.env` file.

2. Run the `app.py` file using the Streamlit CLI. Execute the following command:
   ```
   streamlit run app.py
   ```

3. The application will launch in your default web browser, displaying the user interface.

4. Load multiple PDF documents into the app by following the provided instructions.

5. Ask questions in natural language about the loaded PDFs using the chat interface.

## Project Structure
-----------------
```
.
├── src/
│   ├── __init__.py
│   ├── RAG_retrival_chain.py
│   ├── create_vector_db.py
│   └── detect_and_split_sections.py
│   ├── get_summary.py
│   ├── load_and_extract_text.py
├── static/
│   ├── hero.avif
│   ├── hero2.jpg
│   └── hero3.jpg
├── templates/
│   ├── index.html
├── app.py
├── requirements.txt
└── README.md
```

## Contributing
------------
This repository is intended for educational purposes and does accept further contributions. It serves as supporting material for a github community that demonstrates how to build this project. Feel free to utilize and enhance the app based on your own requirements.

