# Chat with Websites - any data

## Overview

"Chat with Websites" is a Streamlit web application that allows users to interact with the content of a website through a conversational AI interface. This application leverages the LangChain library to load and process website content, split it into manageable chunks, and create a vector store for efficient retrieval of relevant information. Users can ask questions about the website content, and the AI will provide contextually accurate responses.

## Features

- **Load website content**: Enter a URL to load the content from the specified website.
- **Text splitting**: The loaded content is split into smaller chunks for efficient processing and retrieval.
- **Vector store creation**: A vector store is created from the document chunks for fast information retrieval.
- **Conversational interface**: Users can interact with the content through a chat interface.
- **Context-aware responses**: The AI generates responses based on the conversation history and relevant website content.

## Installation

### Prerequisites

Ensure you have the following installed:

- Python 3.8 or later
- pip

### Dependencies

Install the required Python packages using pip:

```bash
pip install streamlit langchain langchain-openai beautifulsoup4 python-dotenv chromadb
```

## Configuration

### OpenAI API Key

This application requires an OpenAI API key to function. Create a `.env` file in the root directory of your project and add your OpenAI API key:

```
OPENAI_API_KEY=your_openai_api_key_here
```

## Usage

### Running the App

To run the Streamlit app, use the following command:

```bash
streamlit run app.py
```

This will start the application and open it in your default web browser.

### Using the App

1. **Enter Website URL**: In the sidebar, enter the URL of the website you want to interact with.
2. **Chat**: Type your message in the chat input box at the bottom of the page and press enter. The AI will respond based on the content of the website and the conversation history.

## Code Explanation

### `get_vectorstore_from_url(url)`

This function takes a URL, loads the content of the website, splits it into smaller chunks, and creates a vector store for efficient retrieval.

### `get_context_retriever_chain(vector_store)`

This function creates a context-aware retriever chain using the loaded vector store and an instance of the ChatOpenAI language model. It generates search queries based on the conversation history to retrieve relevant information.

### `get_conversational_rag_chain(retriever_chain)`

This function creates a conversational retrieval-augmented generation (RAG) chain that answers user questions based on retrieved context and conversation history.

### `get_response(user_input)`

This function uses the retriever and RAG chains to generate a response to the user's query, incorporating the conversation history and relevant website content.

### Streamlit App Configuration

- **Page Configuration**: Sets the page title and icon.
- **Sidebar**: Allows users to input the website URL.
- **Session State**: Maintains the chat history and vector store across user interactions.
- **Chat Interface**: Displays the conversation between the user and the AI.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgements

- [Streamlit](https://streamlit.io/)
- [LangChain](https://github.com/hwchase17/langchain)
- [OpenAI](https://www.openai.com/)

## Contributing

Contributions are welcome! Please feel free to submit a pull request or open an issue for any bugs or feature requests.

