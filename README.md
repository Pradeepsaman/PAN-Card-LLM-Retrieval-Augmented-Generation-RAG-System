Problem Statement

Large Language Models (LLMs) do not inherently know private or domain-specific data.
Directly querying an LLM may lead to:

Hallucinated responses

Inaccurate domain answers

Lack of grounding in real documents

This project solves the problem by combining semantic retrieval + LLM generation.


Solution Approach

The system follows a Retrieval-Augmented Generation (RAG) architecture:

Load PAN card related dataset

Split text into manageable chunks

Convert text into embeddings

Store embeddings in FAISS vector database

Perform semantic similarity search

Retrieve relevant context

Generate final answer using OpenAI LLM




User Question
     ↓
Embedding Model
(convert question → vector)
     ↓
Vector Database Search
(find relevant documents)
     ↓
Retrieved Context / Data
     ↓
LLM
(question + retrieved data)
     ↓
Final Answer (grounded)
