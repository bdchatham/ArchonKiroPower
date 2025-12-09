# Archon Docs Power

The **Archon Docs Power** is a Kiro power that keeps `.kiro/docs` documentation accurate, structured, and grounded in code for repositories participating in the **Archon** RAG knowledge system.  

It automates the creation, updating, and maintenance of documentation that Archon ingests into its vector knowledge base. Whenever code or architecture changes, this power helps keep the RAG-ready docs in sync with reality.

---

## 🚀 What This Power Does

- Initializes a standard `.kiro/docs` layout in any repo.
- Ensures required doc files exist with a consistent structure:
  - `overview.md`
  - `architecture.md`
  - `operations.md`
  - `api.md`
  - `data-models.md`
  - `faq.md`
- Reads and obeys the repo’s `CLAUDE.md` documentation contract.
- Audits existing documentation for:
  - Accuracy and grounding in code/infra.
  - RAG-friendly structure (clear sections, good chunk boundaries).
- Updates docs when asked, keeping them:
  - Traceable (with sources).
  - Small and coherent.
  - Free of hallucinated or speculative content.

---

## 🧠 How It Works

The power follows a simple model:

1. **Read `CLAUDE.md`**  
   Understands the local documentation rules and any repo-specific constraints.

2. **Manage `.kiro/docs`**  
   Creates missing files, updates stale content, and enforces structure.

3. **Ground everything in code and infra**  
   No invented endpoints or flows. Non-trivial statements are backed by:
   - Source files
   - Infra definitions
   - Existing specs

4. **Optimize for Archon ingestion**  
   Documentation is structured into small, focused sections that make high-quality RAG chunks.

---

## 📦 Installation

Add this power to your Kiro workspace:

```bash
kiro power add archon-docs
````

Or include it in your `kiro.yaml`:

```yaml
powers:
  - archon-docs
```

---

## 🛠 Usage

Once installed, activate it in any repo where you want Archon-ready documentation.

Common flows (names depend on how you wire commands, for example):

```bash
# Initialize .kiro/docs structure
kiro use archon-docs setup
```

```bash
# Audit existing docs for accuracy and gaps
kiro use archon-docs audit
```

```bash
# Update docs after changes
kiro use archon-docs update
```

You can alias these or wrap them in your own scripts/automation.

---

## 📁 Expected Repo Layout

A repo using this power typically looks like:

```text
CLAUDE.md
.kiro/
  docs/
    overview.md
    architecture.md
    operations.md
    api.md
    data-models.md
    faq.md
```

Archon ingests the Markdown files under `.kiro/docs`, giving you a consistent, predictable RAG surface across repos.

---

## 📑 Relationship to `CLAUDE.md`

* `CLAUDE.md` is the **contract**.
* The Archon Docs Power is the **enforcer**.

Rules of thumb:

* If `CLAUDE.md` exists, the power defers to its instructions.
* If it doesn’t exist, the power can scaffold a minimal Archon-style `CLAUDE.md`.
* `CLAUDE.md` controls:

  * What must be documented.
  * Acceptable sources of truth.
  * Security and redaction rules.
  * Repo-specific overrides.

---

## 🤝 Why Use This?

Archon aims to build a consistent, queryable semantic layer over your software systems.
This power helps by ensuring:

* Documentation is always fresh and tied to real code.
* Teams follow a consistent structure across repos.
* Docs are auditably correct and source-linked.
* RAG retrieval quality improves dramatically.
* New repos are “Archon-ready” from day one.

---

## 🔒 Security

* No secrets, tokens, or credentials should be written into `.kiro/docs` or `CLAUDE.md`.
* If sensitive content is detected, treat it as a red flag and surface it for human review instead of committing it.

---

## 📄 License

MIT License (or update as appropriate for your org).
