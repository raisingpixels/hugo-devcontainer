# Hugo Parent Developer Devcontainer

A complete VSCode devcontainer setup optimized for Hugo development and content
creation by parent developers who code in fragmented time.

## Quick Start

### Option 1: Existing Hugo Project

1. **Clone this repository** and copy the `.devcontainer/` directory into your
   existing Hugo project:

    ```bash
    git clone https://github.com/raisingpixels/hugo-devcontainer.git
    cd hugo-devcontainer
    cp -r .devcontainer/ /path/to/your/hugo/project/
    cd /path/to/your/hugo/project/
    ```

2. **Update your details** in `devcontainer.json` (replace email and name in `postCreateCommand`)
3. **Open in VSCode** and select "Reopen in Container" when prompted
4. **Start writing** - everything is pre-configured!

### Option 2: Fresh Hugo Site

1. **Clone this repository** as your new project:

   ```bash
   git clone https://github.com/raisingpixels/hugo-devcontainer.git my-hugo-site
   cd my-hugo-site
   ```

2. **Remove git history** and start fresh:

   ```bash
   rm -rf .git
   git init
   ```

3. **Update your details** in `.devcontainer/devcontainer.json` (replace email and name in `postCreateCommand`)
4. **Open in VSCode** and select "Reopen in Container" when prompted
5. **Initialize a new Hugo site** in the container:

   ```bash
   hugo new site . --force
   git add .
   git commit -m "Initial Hugo site"
   ```

6. **Add a theme** and start writing!

## What's Included

### 🤖 AI Assistants

- **Claude Code** - Perfect for understanding Hugo templates and shortcodes
  after days away
- **GitHub Copilot** - Smart completions for Markdown, YAML frontmatter, and Go
  templates
- **Copilot Chat** - Ask questions about Hugo configuration and troubleshooting

### ✍️ Content Creation Tools

- **Markdown linting and preview** with GitHub-style rendering
- **Spell checker** with common Hugo/tech terms pre-added
- **Smart markdown formatting** with proper line wrapping for readability
- **YAML support** for frontmatter and configuration files

### 🎨 Hugo Development

- **Hugo language support** for templates and shortcodes
- **Auto-preview** on port 1313 with proper labeling
- **File nesting** to group config files and drafts
- **Smart exclusions** - hides `public/` and `resources/` from search

### 👨‍👩‍👧‍👦 Parent Developer Optimizations

- **Auto-save after 1 second** - never lose work when interrupted
- **Smart git commits** - stage and commit in one action
- **Auto dark mode** - switches between "Quiet Light" and "Monokai Dimmed" with your system
- **Enhanced prompt** - shows current folder and git branch clearly
- **Persistent bash history** across container rebuilds

## Getting Started with Hugo

### First Time Setup

```bash
# Create a new Hugo site (if needed)
hugo new site my-blog
cd my-blog

# Initialize git (if needed)
git init
git add .
git commit -m "Initial commit"

# Start the development server
hugo server -D --bind 0.0.0.0
```

### Daily Workflow

```bash
# Create a new post
hugo new content/posts/my-post.md

# Start dev server (with drafts)
dev  # alias for hugo server -D --bind 0.0.0.0

# Quick save your work
save  # alias for git add . && git commit -m 'WIP' && git push

# Deploy (if configured)
hugo && git add . && git commit -m "Deploy" && git push
```

## Included Bash Aliases

```bash
# Emergency git workflows
save     # Quick WIP commit and push
quickfix # Pull, commit, and push in one command
backup   # Backup before trying something risky

# Hugo shortcuts
dev      # Start Hugo dev server
build    # Build the site
serve    # Alternative server command

# Navigation
ll       # Better file listing
..       # Go up one directory
...      # Go up two directories

# Git helpers
last     # Show last 5 commits
status   # Git status + recent commits
main     # Switch to main branch and pull
```

## Customization

### Adding Your Own Aliases

Edit `.devcontainer/bashrc` and add:

```bash
alias newpost="hugo new content/posts/$(date +%Y-%m-%d)-"
alias deploy="hugo && git add . && git commit -m 'Deploy' && git push"
```

### Theme-Specific Extensions

Add theme-specific extensions to the `extensions` array in `devcontainer.json`.
For example, for Tailwind CSS themes:

```json
"bradlc.vscode-tailwindcss"
```

### Custom Spell Check Words

Add project-specific terms to the `cSpell.words` array in the settings.

## Troubleshooting

**Port 1313 not accessible?**

- Check if Hugo server is running with `--bind 0.0.0.0`
- Use the `dev` alias which includes the correct binding

**Extensions not installing?**

- Rebuild the container: `Cmd+Shift+P` → "Dev Containers: Rebuild Container"

**Git credentials not working?**

- Set up GitHub CLI: `gh auth login` in the terminal

**Markdown preview not working?**

- Right-click on .md file → "Open Preview to the Side"

## Why This Setup Works for Parent Developers

- **⚡ Instant Environment**: Clone any Hugo project and be productive in 30 seconds
- **🔄 Consistent Everywhere**: Works identically on your laptop, the family computer, or Codespaces
- **🛡️ Never Lose Work**: Auto-save and smart git workflows protect your progress
- **🧠 Context Recovery**: AI assistants help you remember what you were working on
- **👀 Easy on the Eyes**: Comfortable themes for both day and night writing sessions

## Contributing

This devcontainer is part of the [raisingpixels.dev](https://raisingpixels.dev) parent developer resources. Found an improvement? Open an issue or PR!

## License

MIT - Use this however it helps your parent developer workflow!
