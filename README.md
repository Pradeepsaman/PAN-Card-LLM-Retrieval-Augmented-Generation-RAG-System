Problem Statement

Large Language Models (LLMs) do not inherently possess knowledge of private, domain-specific, or real-time data. As a result, directly querying an LLM can lead to several challenges:

Generation of hallucinated responses
Inaccurate or generic domain-specific answers
Lack of grounding in reliable or structured documents

To address these limitations, this project integrates semantic retrieval with LLM-based generation to produce more accurate and context-aware responses.

Solution Approach

This project implements a Retrieval-Augmented Generation (RAG) architecture to enhance the reliability of LLM outputs.

**Workflow Overview:**

Load PAN card-related dataset
Split the text into smaller, manageable chunks
Convert text data into vector embeddings
Store embeddings in a FAISS vector database
Perform semantic similarity search based on user queries
Retrieve the most relevant contextual information
Generate the final response using an OpenAI LLM


**System Architecture Flow:**


User Question
      ↓
Embedding Model
(Convert question → vector representation)
      ↓
Vector Database Search (FAISS)
(Identify relevant documents)
      ↓
Retrieved Context / Data
      ↓
LLM (OpenAI)
(Combine query + retrieved context)
      ↓
Final Answer (Accurate & Context-Aware)
