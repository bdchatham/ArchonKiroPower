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
Or include it in your kiro.yaml:

yaml
Copy code
powers:
  - archon-docs
🛠 Usage
Once installed, activate it in any repo where you want Archon-ready documentation.

Common commands:

bash
Copy code
kiro use archon-docs setup
Creates missing .kiro/docs files and scaffolds an initial structure.

bash
Copy code
kiro use archon-docs audit
Audits documentation for accuracy, grounding, missing content, and RAG-readiness.

bash
Copy code
kiro use archon-docs update
Updates relevant docs based on recent code or infrastructure changes.

📁 Expected Repo Layout
A repo using this power will contain:

kotlin
Copy code
CLAUDE.md
.kiro/
  docs/
    overview.md
    architecture.md
    operations.md
    api.md
    data-models.md
    faq.md
Archon ingests only the .kiro/docs directory, making documentation predictable and structured across all repositories.

📑 Relationship to CLAUDE.md
CLAUDE.md is the contract.
This power is the enforcer.

If CLAUDE.md exists, the power always defers to its rules.

If it doesn’t exist, the power scaffolds a minimal, contract-compliant version.

CLAUDE.md controls:

What must be documented

Allowed sources of truth

Security guardrails

Repo-specific overrides

🤝 Why Use This?
Archon solves organizational knowledge at scale by building a consistent, queryable semantic layer across all repositories.

This power ensures:

Documentation is always fresh.

Teams follow a consistent structure.

Docs remain grounded and auditably correct.

Archon RAG retrieval becomes dramatically better.

Every repo is RAG-ready on day one.

🔒 Security
This power never stores secrets, credentials, or proprietary endpoints in documentation.
If sensitive content appears, the power marks it for human review rather than committing it.

📄 License
MIT License (or update as desired).

yaml
Copy code

---

If you want, I can also generate:

- A GitHub template repository outline that includes `CLAUDE.md`, `.kiro/docs/*`, and starter files.
- A `power.json` manifest or Kiro CLI configuration.
- A logo/banner for the README.
