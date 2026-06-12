# DocuMind Agent Architecture

```text
                    ┌─────────────────┐
                    │      User       │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │   Any-Agent     │
                    │ Agent Controller│
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │      MCPD       │
                    │ Tool Orchestration
                    └────────┬────────┘
                             │
            ┌────────────────┴────────────────┐
            │                                 │
            ▼                                 ▼
   ┌─────────────────┐               ┌─────────────────┐
   │   Encoderfile   │               │ Internet Search │
   │ Document Search │               │  (Fallback)     │
   └────────┬────────┘               └────────┬────────┘
            │                                 │
            │ Answer Found?                   │
            │                                 │
            ▼                                 │
   ┌─────────────────┐                        │
   │    Llamafile    │◄───────────────────────┘
   │ Local AI Engine │
   └────────┬────────┘
            │
            ▼
   ┌─────────────────┐
   │  Final Response │
   └─────────────────┘
```

## Workflow

1. User uploads local documents (PDF, DOCX, TXT).
2. Encoderfile processes and indexes the documents.
3. User asks a question.
4. Any-Agent receives the query.
5. MCPD routes the request to available tools.
6. Encoderfile searches local documents first.
7. If relevant information is found:

   * Context is sent to Llamafile.
   * Llamafile generates the answer.
8. If no information is found:

   * Internet search is triggered.
   * Results are passed to Llamafile.
9. Final answer is returned to the user.

## Local-First Principle

Local Documents → Local AI → Internet Only When Needed

This ensures:

* Better privacy
* Faster retrieval
* Reduced internet dependency
* Organization-specific knowledge access

```
```
