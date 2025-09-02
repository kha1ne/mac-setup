# macOS 2025 Developer Setup Checklist – Core Package Managers & Base Tools

This checklist focuses only on **base developer essentials** (system-level tooling, not system settings).  
Sources merged from Gabriel Drouin (2025), Robin Wieruch (2025), and Tania Rascia (2024).

---

## 1. Package Managers & Core Tools

- [ ] **Install Xcode Command Line Tools**  
  Provides `git`, compilers, and system headers required for most dev work.  
  ```bash
  xcode-select --install
  ```

- [ ] **Install Homebrew**  
  The package manager for macOS.  
  ```bash
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
  ```

- [ ] **Verify Homebrew Installation**  
  ```bash
  brew doctor
  brew update
  ```

- [ ] **Set up Brewfile for Automation (optional)**  
  Automate re-installation of apps and packages across machines.  
  ```bash
  brew bundle dump --file=~/Brewfile
  brew bundle --file=~/Brewfile
  ```

- [ ] **Install Rosetta 2 (Apple Silicon only)**  
  Required for Intel-based apps on ARM Macs.  
  ```bash
  softwareupdate --install-rosetta
  ```

---

## ✅ Notes

- These are **foundational installs** required by nearly all developer workflows.  
- Everything else (languages, frameworks, utilities) depends on these base tools.  
- Use the **Brewfile** for automation when migrating to a new Mac.

