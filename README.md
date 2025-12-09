# Archon Docs Power

The **Archon Docs Power** is a Kiro power that keeps `.kiro/docs` documentation accurate, structured, and grounded in code for repositories participating in the **Archon** RAG knowledge system.  
It automates the creation, updating, and maintenance of documentation that Archon ingests into its vector knowledge base.

This power acts as the “docs intelligence layer” for your repos: whenever code or architecture changes, the power ensures the RAG-ready documentation stays in sync and follows the Archon documentation contract.

---

## 🚀 What This Power Does

- Initializes a standard `.kiro/docs` layout in any repo.
- Ensures required doc files exist with correct structure:
  - `overview.md`
  - `architecture.md`
  - `operations.md`
  - `api.md`
  - `data-models.md`
  - `faq.md`
- Reads and obeys the repo’s `CLAUDE.md` contract.
- Audits existing documentation for accuracy, grounding, and RAG-friendly structure.
- Updates docs automatically when the user requests changes or when repo structure shifts.
- Produces documentation optimized for retrieval:
  - Clear provenance
  - Small, coherent sections
  - Minimal duplication
  - No hallucination or speculative content

---

## 🧠 How It Works

This power follows a simple model:

1. **Read the repo’s `CLAUDE.md`**  
   Defines the documentation contract and any repo-specific rules.

2. **Manage `.kiro/docs`**  
   Creates missing docs, updates stale ones, and enforces structure.

3. **Ground everything in code + infra**  
   No invented behavior, no speculative architecture.  
   All non-trivial statements include **Source** references (files/paths).

4. **Optimize for Archon ingestion**  
   Docs are structured to become high-quality semantic chunks for RAG.

---

## 📦 Installation

Add this power to your Kiro workspace:

```bash
kiro power add archon-docs
