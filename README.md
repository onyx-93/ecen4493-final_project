# LLM for SystemVerilog Code Generation

A domain-specific Retrieval-Augmented Generation (RAG) system designed to generate accurate, synthesizable SystemVerilog code.

## Overview

General-purpose LLMs frequently hallucinate or produce non-synthesizable HDL code due to the limited representation of hardware description languages in their training data. **RAG** addresses this by grounding responses in a custom knowledge base of SystemVerilog documentation, academic materials, and real hardware implementations.

This project was developed as part of the final project for my computer engineering course, ECEN 4493 - AI in Engineering, at Oklahoma State University.

## Features

- **Specialized SystemVerilog Knowledge Base** – Loads PDFs, `.sv` files, and documentation
- **Local LLM Integration** – Uses Ollama (Llama 3 8B by default) for fully local operation
- **Vector Search** – Powered by ChromaDB with Nomic embeddings
- **Response Logging** – All generations are saved with timestamps for review
- **Robust Document Processing** – Handles PDFs and SystemVerilog source files with smart chunking

## Knowledge Base

The system is powered by a custom knowledge base that includes:
- Academic lecture notes and project documentation
- SystemVerilog reference materials
- High-quality, real-world RTL examples from the **[CORE-V Wally RISC-V Processor](https://github.com/openhwgroup/cvw)** (OpenHW Group)

## Attribution & Thanks

This project makes use of source files and documentation from the **[openhwgroup/cvw](https://github.com/openhwgroup/cvw)** repository — the official home of the **CORE-V Wally** configurable RISC-V processor. 

I would like to thank the OpenHW Group and the Wally development team for providing such a high-quality open-source SystemVerilog codebase.

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

1. **Knowledge Base**
   ```bash
   git clone <repo-url>
   cd sv-rag
