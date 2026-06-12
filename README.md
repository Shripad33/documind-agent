# DocuMind Agent

## Overview

DocuMind Agent is a document-first AI assistant built for the Mozilla.ai Hackathon.

The system prioritizes local private documents before accessing public internet resources. Users can upload documents and ask questions in natural language. The agent first searches local knowledge sources and only performs internet searches when the required information is unavailable locally.

This approach improves privacy, reduces unnecessary internet dependency, and enables faster access to organization-specific information.

---

## Problem Statement

Build an agent that answers questions from private local documents first, then reaches out to the public internet only when necessary using:

* Encoderfile
* Llamafile
* MCPD
* Any-Agent

---

## Solution

DocuMind Agent follows a Local-First AI architecture.

1. User uploads local documents.
2. Documents are indexed and made searchable.
3. User asks a question.
4. Agent searches local documents first.
5. If an answer is found:

   * Generate response using local context.
6. If no answer is found:

   * Trigger internet search fallback.
7. Return the final response to the user.

---

## Features

* Document-first retrieval
* Local AI inference
* Internet fallback mechanism
* Fast document search
* Privacy-focused architecture
* Chat-based interaction
* Support for TXT, PDF, and DOCX files
* Modern responsive interface

---

## Architecture

User
↓
Any-Agent
↓
Encoderfile Document Retrieval
↓
Answer Found?
├── Yes → Llamafile Response
└── No → Internet Search
↓
Final Answer

---

## Tech Stack

Frontend

* React
* Tailwind CSS

Backend

* FastAPI
* Python

AI Stack

* Encoderfile
* Llamafile
* MCPD
* Any-Agent

Storage

* Local Document Store

---

## Project Structure

documind-agent/

├── frontend/

├── backend/

├── docs/

├── screenshots/

├── architecture/

├── README.md

├── requirements.txt

└── LICENSE

---

## Demo Questions

### Local Document Questions

* What are office hours?
* How many leave days are available?
* What is the project deadline?

### Internet Fallback Questions

* What is the capital of Japan?
* Who is the Prime Minister of India?
* What is Artificial Intelligence?

---

## Future Improvements

* Voice-based querying
* Multi-document retrieval
* Real-time collaboration
* Advanced semantic search
* Local knowledge graph generation

---

## Team

Built for Mozilla.ai Hackathon 2026.

## License

MIT License
