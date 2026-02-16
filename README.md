# End-To-End-Multimodal-Azure-Deployment-With-Observability-And-Orchestration-Engine
Building an AI-powered compliance auditing platform that automatically evaluates video advertisements against regulatory standards. The system enables organisations to detect violations, reduce manual review effort, and ensure faster, scalable compliance decisions.

## Description
This project implements an end-to-end, production-oriented Video Compliance QA system that automates regulatory auditing of unstructured video content.

The pipeline leverages Azure Video Indexer for multimodal extraction (transcripts and OCR), which is enriched through a Retrieval-Augmented Generation (RAG) framework using Azure OpenAI embeddings and Azure AI Search for semantic retrieval of compliance rules.

A LangGraph-orchestrated workflow coordinates ingestion, retrieval, and reasoning, enabling deterministic and modular execution across the pipeline. The core reasoning layer, powered by GPT-4o, evaluates contextual data to identify compliance violations and generate structured, actionable JSON reports.

To ensure production readiness, the system incorporates LangSmith for LLM tracing and debugging and Azure Application Insights for logging, telemetry, and real-time performance monitoring, providing full-stack observability.


# System Architecture
<img width="1402" height="817" alt="image" src="https://github.com/user-attachments/assets/93e80b1d-50e9-41e6-b8dc-0cfc5d78378e" />

## 🧠 How the System Works

This system automates compliance auditing of video advertisements by combining multimodal processing, retrieval-augmented reasoning, and agentic orchestration.

---

### 🔄 End-to-End Workflow

1. **Input (User Trigger)**
   - User provides a YouTube video URL (e.g., advertisement content)
   - FastAPI backend triggers the audit pipeline

2. **Video Ingestion & Processing**
   - Video is downloaded using a Python ingestion script  
   - Uploaded to **Azure Video Indexer**, which extracts:
     - Transcripts (speech-to-text)
     - OCR (on-screen text)
     - Visual metadata  

3. **Retrieval Layer (Regulatory Context)**
   - Compliance rules (PDFs) are indexed in **Azure AI Search**
   - Documents are embedded using **Azure OpenAI embeddings**
   - Hybrid vector search retrieves the most relevant regulatory clauses  

4. **Reasoning Engine (LLM Evaluation)**
   - Extracted video content (transcripts + OCR) is combined with retrieved rules  
   - **GPT-4o** evaluates whether the content violates compliance standards  
   - Detects misleading claims or missing disclosures  

5. **Agentic Workflow (LangGraph)**
   - LangGraph orchestrates the full pipeline:
     - ingestion → retrieval → reasoning → reporting  
   - Ensures modular, traceable, and deterministic execution  

6. **Output (Compliance Report)**
   - Generates structured JSON output:
     - Pass / Fail verdict  
     - Detected violations  
     - Suggested corrections  

7. **Monitoring & Observability**
   - **Azure Application Insights**:
     - Tracks latency, failures, and system health  
   - **LangSmith**:
     - Provides detailed tracing of LLM interactions and reasoning chains  

---

## ☁️ Infrastructure & Components

| Component | Purpose |
|----------|--------|
| **Azure Blob Storage** | Stores raw and processed data (transcripts, video artifacts) |
| **Azure Video Indexer** | Extracts transcripts, OCR, and video insights |
| **Azure OpenAI (GPT-4o + Embeddings)** | Core reasoning engine + semantic representation |
| **Azure AI Search** | Vector database for compliance rules (PDFs) |
| **Azure Application Insights** | Monitoring, logging, and performance tracking |
| **LangSmith** | Observability and tracing for LLM workflows |
| **FastAPI Backend** | Handles API requests and pipeline triggering |
| **LangGraph** | Orchestrates agentic workflow execution |

---

## 💡 Key Idea

Unlike traditional systems, this pipeline does not “watch” videos like humans.  
Instead, it transforms video into structured data (text + metadata), enriches it with regulatory context, and uses LLM reasoning to make compliance decisions at scale.

---
