# Conversational Chatbot with Document Retrieval and External Search Integration

This repository contains the implementation of a conversational chatbot that leverages document retrieval, external search tools, and LLM (Language Model) capabilities. The chatbot is designed to answer user queries based on a preloaded set of news articles, as well as information retrieved from Wikipedia and DuckDuckGo.

Drive Link : https://drive.google.com/drive/folders/1E04K_XsOaSGK0tWbah_o-KbvS_xEFQk-?usp=sharing

## Table of Contents

- [Overview](#overview)
- [Installation](#installation)
- [Usage](#usage)
- [Code Explanation](#code-explanation)
  - [Loading and Splitting Documents](#loading-and-splitting-documents)
  - [Creating the Vector Store](#creating-the-vector-store)
  - [Setting up the Language Model](#setting-up-the-language-model)
  - [Conversational Chain](#conversational-chain)
  - [Integrating Wikipedia and DuckDuckGo](#integrating-wikipedia-and-duckduckgo)
- [Running the Chatbot](#running-the-chatbot)
- [License](#license)

## Overview

This project involves several key components:
1. **Document Loading and Splitting**: News articles are loaded and split into smaller chunks.
2. **Embedding Creation and Vector Store**: The document chunks are embedded using a sentence transformer model and stored in a FAISS vector store.
3. **Conversational Chain**: A conversational chain is created using a language model (Llama 2) and the vector store for retrieval.
4. **External Search Integration**: Wikipedia and DuckDuckGo search tools are integrated to enhance the chatbot's responses.

## Installation

1. Clone the repository:
    ```bash
    git clone [https://github.com/your-username/repository-name.git](https://github.com/Idk507/Multi_Agent_QA_ChatBot_llama2)
    cd repository-name
    ```

2. Install the required Python packages:
    ```bash
    pip install -r requirements.txt
    ```

3. Ensure you have the necessary models and data files:
    - Llama-2-7B-chat model: `llama-2-7b-chat.ggmlv3.q8_0.bin`
    - News articles: `news.article.json`

## Usage

To run the chatbot, execute the following command:
```bash
python chatbot.py
```


## Code Explanation

# Loading and Splitting Documents
* Loading Documents: The code begins by loading a set of news articles from a JSON file.
* Splitting Documents: Each article is split into smaller chunks using a text splitter. This is done to facilitate more efficient and accurate retrieval of relevant information during user queries.

# Creating the Vector Store
* Embedding Creation: The document chunks are transformed into numerical embeddings using a sentence transformer model (sentence-transformers/all-MiniLM-L6-v2).
* Vector Store: These embeddings are stored in a FAISS vector store, which allows for efficient similarity search and retrieval of relevant chunks based on user queries.

# Setting up the Language Model
* Model Configuration: The chatbot uses the Llama-2-7B-chat model, configured with specific parameters for generating responses.
* Memory Management: A conversation buffer memory is used to keep track of the conversation history, ensuring the chatbot can provide contextually relevant responses.

#Conversational Chain
* Conversational Chain Setup: A conversational retrieval chain is created, combining the language model and the vector store. This allows the chatbot to retrieve relevant document chunks and generate coherent responses based on them.
* User Interaction: The chatbot handles user queries, retrieves relevant information from the vector store, and generates responses while maintaining the conversation history.

# Integrating Wikipedia and DuckDuckGo
* External Search Tools: The chatbot integrates Wikipedia and DuckDuckGo search tools to enhance its responses with additional information not covered in the preloaded documents.
* Search Execution: For each user query, the chatbot performs searches on Wikipedia and DuckDuckGo, providing supplementary information along with its generated response.

# Running the Chatbot
* Interactive Session: Start the chatbot and enter your queries. The chatbot will provide responses based on the document retrieval and external search results.
* Ending the Session: Type exit to end the conversation.
