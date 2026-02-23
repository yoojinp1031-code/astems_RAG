# 🤖 astems_RAG

> A collection of RAG (Retrieval-Augmented Generation) implementations for an internal chatbot at Astems, designed to assist with After-Service (AS) record retrieval and explanation.

## 🛠️ Development Environment
- **Vector DB**: PostgreSQL Vector DB on Docker Container
- **LLM**: OpenAI API

---
## 📦 Dependencies

| Package | Usage |
|---------|-------|
| `langchain` | RAG pipeline framework |
| `langchain-openai` | OpenAI LLM & Embeddings |
| `langchain-postgres` | PGVector integration |
| `langchain-google-genai` | Google Gemini LLM & Embeddings |
| `langchain-community` | Document loaders, retrievers |
| `psycopg2` | PostgreSQL connector |
| `pandas` | Excel data preprocessing |
| `python-dotenv` | Environment variable management |
| `PyMuPDF` | PDF loading |
| `tqdm` | Progress bar |
| `requests` | API calls |
---


## 🎯 Project Overview

This repository contains source code for a **RAG-based chatbot** that allows users to query internal AS (After-Service) history data in natural language.

The chatbot retrieves relevant AS records and generates context-aware explanations, replacing manual document searches with an intelligent conversational interface.

**Key challenges addressed:**
- Unstructured AS records in Excel format required preprocessing and metadata generation before embedding
- Multiple retrieval strategies were explored and benchmarked to optimize response accuracy
- Hybrid search combining vector similarity and full-text search was adopted to handle both semantic and keyword-based queries

---

## 📂 AS Excel Data RAG

| File | Description |
|------|-------------|
| `SI_AS_Embedding` | Processes and refines AS records from Excel files, generates metadata, and embeds them into the vector DB |
| `SI_AS_Simple` | Naive RAG implementation |
| `SI_AS_Ensemble` | Hybrid Retriever combining vector search and full-text search (PostgreSQL Full Text Retriever). Used for performance evaluation across OpenAI models |
| `SI_AS_RAG_TimeW` | Time Weighted Re-ranking Retriever |
| `SI_AS_SelfQuerying` | Two-stage LLM pipeline that filters and refines user queries before retrieval |

---

## 📂 Bookstack Blog Data RAG

| File | Description |
|------|-------------|
| `Bookstack_family_Emb_v2` | Converts Bookstack blog posts from MD to JSON, generates metadata with URLs, and embeds using parent-child document chunking |
| `Bookstack_family_use_v3` | Retrieval code using parent-child document structure, updated to include short parent documents without child documents |

---
