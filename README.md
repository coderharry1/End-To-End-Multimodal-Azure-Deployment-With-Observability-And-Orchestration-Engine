# End-To-End-Multimodal-Azure-Deployment-With-Observability-And-Orchestration-Engine
Built a LangGraph-based Video Compliance QA pipeline using RAG to audit content against regulatory standards. Leveraged Azure Video Indexer, AI Search, and GPT-4o to generate structured compliance reports, with LangSmith tracing and Application Insights for end-to-end monitoring.

## Description
This project establishes an automated Video Compliance QA Pipeline orchestrated by LangGraph, designed to audit content against regulatory standards using a RAG architecture. We leverage Azure Video Indexer for multimodal ingestion (transcripts/OCR) and Azure AI Search to retrieve relevant compliance rules via Azure OpenAI Embeddings. The core reasoning engine, Azure OpenAI (GPT-4o), synthesizes this data to deterministically detect violations, while LangSmith provides granular tracing for LLM workflow optimization. Additionally, Azure Application Insights is integrated for production-grade telemetry, logging, and real-time performance monitoring. This end-to-end system transforms unstructured video into structured, actionable JSON compliance reports with deep full-stack observability.

# System Architecture
<img width="1402" height="817" alt="image" src="https://github.com/user-attachments/assets/93e80b1d-50e9-41e6-b8dc-0cfc5d78378e" />
