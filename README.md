# SV-RAG: SystemVerilog RAG Assistant

A domain-specific Retrieval-Augmented Generation (RAG) system designed to generate accurate, synthesizable SystemVerilog RTL code.

## Overview

General-purpose LLMs frequently hallucinate or produce non-synthesizable HDL code due to the limited representation of hardware description languages in their training data. **SV-RAG** addresses this by grounding responses in a custom knowledge base of SystemVerilog documentation, academic materials, and real hardware implementations.

This project was developed as part of a university hardware design course (HW5) to demonstrate the effectiveness of RAG for specialized technical domains like digital hardware engineering.

## Features

- **Specialized SystemVerilog Knowledge Base** – Loads PDFs, `.sv` files, and documentation
- **Local LLM Integration** – Uses Ollama (Llama 3 8B by default) for fully local operation
- **Vector Search** – Powered by ChromaDB with Nomic embeddings
- **Hardware-Aware Prompting** – Strict rules for synthesizable RTL (no delays, proper port declarations, etc.)
- **Interactive CLI** – Ask for modules, gates, or complex designs and get complete, ready-to-use code
- **Response Logging** – All generations are saved with timestamps for review
- **Robust Document Processing** – Handles PDFs and SystemVerilog source files with smart chunking

## Project Goals

- Reduce hallucinations in HDL generation
- Enforce synthesizable coding practices
- Provide accurate, professional-grade SystemVerilog modules
- Serve as a foundation for further validation pipelines (e.g., Verilator integration)

## Tech Stack

- **LangChain** – Orchestration and RAG pipeline
- **ChromaDB** – Vector store
- **Ollama** – Local LLM and embeddings (`nomic-embed-text`, `llama3:8b`)
- **PyPDFLoader + TextLoader** – Document ingestion
- **RecursiveCharacterTextSplitter** – Smart chunking optimized for HDL

## Installation & Setup

1. **Clone the repository**
   ```bash
   git clone <repo-url>
   cd sv-rag
