# End-To-End-Multimodal-Azure-Deployment-With-Observability-And-Orchestration-Engine
Built a production-grade Video Compliance QA pipeline using LangGraph and RAG to audit multimodal content against regulatory standards. The system integrates Azure Video Indexer, AI Search, and GPT-4o to generate structured compliance reports with end-to-end observability via LangSmith and Application Insights.

## Description
This project implements an end-to-end, production-oriented Video Compliance QA system that automates regulatory auditing of unstructured video content.

The pipeline leverages Azure Video Indexer for multimodal extraction (transcripts and OCR), which is enriched through a Retrieval-Augmented Generation (RAG) framework using Azure OpenAI embeddings and Azure AI Search for semantic retrieval of compliance rules.

A LangGraph-orchestrated workflow coordinates ingestion, retrieval, and reasoning, enabling deterministic and modular execution across the pipeline. The core reasoning layer, powered by GPT-4o, evaluates contextual data to identify compliance violations and generate structured, actionable JSON reports.

To ensure production readiness, the system incorporates LangSmith for LLM tracing and debugging and Azure Application Insights for logging, telemetry, and real-time performance monitoring, providing full-stack observability.


# System Architecture
<img width="1402" height="817" alt="image" src="https://github.com/user-attachments/assets/93e80b1d-50e9-41e6-b8dc-0cfc5d78378e" />
