# DevEnv - Universal Development Environment Manager

One tool to manage ALL your development environment versions. Stop juggling pyenv, nvm, rbenv, and a dozen other tools!

## Why DevEnv?

**The Problem:** Every language has its own version manager with its own commands:
- Python → pyenv
- Node → nvm
- Ruby → rbenv
- Java → update-alternatives
- Go → manual installs

**The Solution:** ONE consistent interface for everything!

```bash
devenv use python 3.11
devenv use node 18
devenv status
```

## Installation

```bash
curl -sSL https://raw.githubusercontent.com/YOUR_USERNAME/devenv/main/install.sh | bash
```

## Quick Start

```bash
# See what's currently active
devenv status

# Switch versions
devenv use python 3.11
devenv use node 18

# Auto-detect project requirements
devenv detect

# List available versions
devenv list python
```

## Commands

```
use <lang> <version>    Switch to a version
status                  Show all active versions
current <lang>          Show current version
list <lang>             List available versions
detect                  Auto-detect from project files
```

## Supported Languages

✅ **Python** (via pyenv or system)  
✅ **Node.js** (via nvm or system)  
✅ **Java** (via update-alternatives)  
✅ **Ruby** (via rbenv or system)  
✅ **Go** (via system)  

## Features

🔄 **Consistent interface** - Same commands for all languages  
🎯 **Auto-detection** - Reads .python-version, .nvmrc, etc.  
📊 **Clear status** - See all active versions at once  
⚡ **Fast switching** - Change versions instantly  
🔧 **Wraps existing tools** - Uses pyenv, nvm, rbenv under the hood  
📝 **Project aware** - Detects requirements from project files  

## Examples

**Switch Python version:**
```bash
devenv use python 3.11
# ✓ Python switched to 3.11
# ℹ Current: 3.11.0
```

**Check all versions:**
```bash
devenv status
# Python:  3.11.0
# Node:    18.17.0
# Java:    17.0.2
# Ruby:    3.2.0
# Go:      1.21.0
```

**Auto-detect project needs:**
```bash
cd myproject
devenv detect
# ✓ Found .python-version: 3.11
# ℹ Run: devenv use python 3.11
# ✓ Found package.json (Node project)
# ℹ Required Node: >=18.0.0
```

## Supported Project Files

DevEnv auto-detects versions from:
- `.python-version`
- `.nvmrc`
- `.node-version`
- `.ruby-version`
- `package.json` (engines field)
- `pyproject.toml`
- `.tool-versions` (asdf compatible)

## How It Works

DevEnv is a smart wrapper that:
1. Checks if you have the appropriate version manager (pyenv, nvm, etc.)
2. Uses that tool to switch versions
3. Provides helpful guidance if tools aren't installed
4. Works with system versions as fallback

## Requirements

DevEnv works best with these version managers installed:
- **pyenv** for Python: `curl https://pyenv.run | bash`
- **nvm** for Node: `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash`
- **rbenv** for Ruby: `curl -fsSL https://github.com/rbenv/rbenv-installer/raw/main/bin/rbenv-installer | bash`

But will work with system versions if these aren't available!

## Comparison

| Task | Without DevEnv | With DevEnv |
|------|---------------|-------------|
| Switch Python | `pyenv global 3.11` | `devenv use python 3.11` |
| Switch Node | `nvm use 18` | `devenv use node 18` |
| Switch Ruby | `rbenv global 3.2` | `devenv use ruby 3.2` |
| Check versions | Multiple commands | `devenv status` |
| Detect project | Manual inspection | `devenv detect` |

## Roadmap

- [x] Version switching for Python, Node, Ruby, Java, Go
- [x] Status overview
- [x] Project detection
- [ ] Auto-install missing versions
- [ ] Dependency management integration
- [ ] Project-specific environments (.devenv file)
- [ ] Shell integration for auto-switching

## License

MIT License - see [LICENSE](LICENSE)

## Author

Sean - [@strabo231](https://github.com/strabo231)

---

**One tool. All languages. Simple.** 🚀
