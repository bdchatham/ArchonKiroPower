# Archon Docs Power

A Kiro Power for maintaining accurate, RAG-ready `.kiro/docs` documentation for Archon across all participating repositories.

## What This Power Does

This power helps you:
- Initialize and maintain `.kiro/docs` structure in Archon repositories
- Ensure documentation is grounded in code and infrastructure
- Follow RAG-friendly documentation patterns
- Maintain the Archon documentation contract via `CLAUDE.md`

## Installation

### From GitHub

Add this repository in Kiro's Powers UI:

1. Open Kiro Powers panel
2. Click "Available Powers" → "Manage Repos" → "Add Repository"
3. Select "Git Repository"
4. Enter URL: `https://github.com/bdchatham/ArchonKiroPower`
5. The power will be available as "Archon RAG Documentation"

### From Local Directory (Development)

For local testing:

1. Clone this repository
2. In Kiro Powers UI: "Available Powers" → "Manage Repos" → "Add Repository"
3. Select "Local Directory"
4. Point to the `archon-docs` subdirectory in this repo

## Repository Structure

```
ArchonKiroPower/
├── archon-docs/          # The actual power (clean, installable)
│   └── POWER.md          # Power documentation and instructions
├── dist/                 # Build artifacts (gitignored)
├── .gitignore           # Git ignore rules
├── README.md            # This file
└── package-power.sh     # Build script (if needed)
```

## Power Structure

The power follows Kiro's power specification:
- **POWER.md**: Complete documentation with frontmatter metadata
- No `mcp.json`: This is a Knowledge Base Power (pure documentation)
- No `steering/`: All content fits in POWER.md

## Development

The `archon-docs/` directory contains only the files allowed in a Kiro Power:
- `POWER.md` (required)

Development and build files are kept at the repository root and excluded from the power package.

## Usage

Once installed, activate the power when working on Archon repositories:

```
"Set up Archon docs for this repo"
"Update docs after infrastructure changes"
"Audit .kiro/docs for accuracy"
```

The power will guide you through maintaining RAG-ready documentation that follows the Archon contract.

## Author

Brandon Chatham (@bdchatham)

## License

MIT
