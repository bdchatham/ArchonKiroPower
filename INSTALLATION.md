# Installation Guide

## Install from GitHub (Recommended)

Your power is now properly structured and ready to install from GitHub!

### Method 1: Install via GitHub URL

1. Open Kiro
2. Open Powers panel (use command palette or sidebar)
3. Click "Available Powers" → "Manage Repos" → "Add Repository"
4. Select "Git Repository"
5. Enter: `https://github.com/bdchatham/ArchonKiroPower`
6. Click "Add"
7. The "Archon RAG Documentation" power will appear in your available powers
8. Click "Install" to activate it

### Method 2: Install Specific Subdirectory (Alternative)

If you want to be explicit about the subdirectory:

1. Follow steps 1-4 above
2. Enter: `https://github.com/bdchatham/ArchonKiroPower/tree/main/archon-docs`
3. Continue with steps 6-8

## Install from Local Directory (Development/Testing)

For local development and testing:

1. Clone this repository:
   ```bash
   git clone https://github.com/bdchatham/ArchonKiroPower.git
   cd ArchonKiroPower
   ```

2. In Kiro:
   - Open Powers panel
   - Click "Available Powers" → "Manage Repos" → "Add Repository"
   - Select "Local Directory"
   - Browse to and select the `archon-docs` subdirectory
   - Click "Add"

3. The power will appear in your available powers list
4. Click "Install" to activate it

## Verify Installation

After installation, verify the power is working:

1. Open a repository that should use Archon documentation
2. In Kiro chat, try: "Set up Archon docs for this repo"
3. The power should activate and guide you through the setup

## Troubleshooting

### "No valid power found in the repository"

This means Kiro couldn't find a valid POWER.md file. Make sure:
- You're pointing to the repository root or the `archon-docs` subdirectory
- The repository is public (for GitHub URLs)
- The POWER.md file has valid frontmatter

### "Power validation failed: Power contains disallowed files"

This should no longer happen with the new structure. The `archon-docs/` subdirectory contains only `POWER.md`, which is the only required file for this Knowledge Base Power.

### Power doesn't activate when expected

Check the keywords in POWER.md. The power activates when you mention:
- archon
- rag
- documentation
- system-architecture
- runbooks
- kiro

Try explicitly mentioning these terms in your chat messages.

## Updating the Power

If you make changes to the power:

1. Edit `archon-docs/POWER.md`
2. Commit and push:
   ```bash
   git add archon-docs/POWER.md
   git commit -m "Update power documentation"
   git push origin main
   ```

3. In Kiro Powers panel:
   - Find the "Archon RAG Documentation" power
   - Click the refresh/update button
   - Or remove and re-add the repository

## Repository Structure

```
ArchonKiroPower/
├── archon-docs/          # ← The actual power (clean, installable)
│   └── POWER.md          # ← Power documentation
├── dist/                 # Build artifacts (gitignored)
├── .gitignore
├── INSTALLATION.md       # This file
├── README.md
├── POWER.md              # Development copy
└── package-power.sh      # Build script
```

Only the `archon-docs/` directory is used for power installation. Other files are for development and documentation.
