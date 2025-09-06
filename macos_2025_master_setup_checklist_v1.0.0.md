# macOS 2025 Full Developer Setup Checklist

**Version:** 1.0.0  
**Release date:** 2025-09-06  
**Maintainer:** Marko Maric  
**Change control:** Semantic Versioning (MAJOR.MINOR.PATCH)

---

## 🔖 Versioning Rules
- **MAJOR**: Breaking structure changes (section order, removals, incompatible steps).  
- **MINOR**: Backward-compatible additions (new apps, optional steps, notes).  
- **PATCH**: Fixes/typos, safer commands, minor clarifications.  

For each update:
1) Bump version above, 2) Update **Changelog**, 3) Save as a new file (e.g., `_v1.1.0.md`).

---

## 📑 Table of Contents
- [Changelog](#changelog)
- [0. System Settings](#0-system-settings) (v1.0.0)
- [1. Core Tools](#1-core-tools) (v1.0.0)
- [2. Shell & Terminal](#2-shell--terminal) (v1.0.0)
- [3. Languages & Runtimes](#3-languages--runtimes) (v1.0.0)
- [4. Development Tools & IDEs](#4-development-tools--ides) (v1.0.0)
- [5. Productivity & Communication](#5-productivity--communication) (v1.0.0)

---

## Changelog

### 1.0.0 — 2025-09-06
- Initial consolidated release with TOC.  
- Sections included:
  - 0. System Settings (gold standard merged settings)
  - 1. Core Tools (admin-level Brew, Xcode CLI, Rosetta)
  - 2. Shell & Terminal (iTerm2, Oh My Zsh, Dracula)
  - 3. Languages & Runtimes (nvm + pyenv → latest)
  - 4. Dev Tools & IDEs (VS Code, PyCharm, Git + GitHub SSH)
  - 5. Productivity & Communication (Office 365, Teams, Chrome, IINA, XnView MP, Spotify, Sublime Text, Keka, Araxis Merge + Fork integration, Double Commander)

---

# macOS 2025 Full Developer Setup Checklist

This document consolidates all setup steps (#0–#7) into a single reference.  
It covers system settings, base tools, shell/terminal, runtimes, IDEs, and productivity apps.  

---

## 📑 Table of Contents

- [0. System Settings](#0-system-settings)
- [1. Core Tools](#1-core-tools)
- [2. Shell & Terminal](#2-shell--terminal)
- [3. Languages & Runtimes](#3-languages--runtimes)
- [4. Development Tools & IDEs](#4-development-tools--ides)
- [5. Productivity & Communication](#5-productivity--communication)

---

## 0. System Settings
# macOS 2025 Gold Standard Developer Setup Checklist

A merged checklist combining insights from Gabriel Drouin (2025), Robin Wieruch (2025), 
Tania Rascia (2024), and the Master Setup Checklist (2025).  
Focus: **System Settings only** (no apps or package managers).

---

## 1. Appearance & UI

- [ ] **Enable Dark Mode**  
  System Settings → Appearance → Select *Dark*.

- [ ] **Always Show Scrollbars**  
  System Settings → Appearance → Scroll Bars → *Always*.

- [ ] **Dock Settings**  
  - Auto-hide: System Settings → Desktop & Dock → *Automatically hide and show the Dock*.  
  - Resize icons: Adjust *Size* slider.  
  - Remove apps: Drag out icons.  
  - Keep only essentials.

- [ ] **Remove Recent Applications from Dock**  
  System Settings → Desktop & Dock → Disable *Show recent applications in Dock*.

- [ ] **Hot Corners**  
  System Settings → Desktop & Dock → Hot Corners → Assign actions (Mission Control, Desktop, Lock Screen).

- [ ] **Stage Manager**  
  Control Center → Stage Manager → Enable (optional).

- [ ] **Reduce Motion / Animations**  
  System Settings → Accessibility → Display → Enable *Reduce motion*.

- [ ] **Increase Contrast** (optional)  
  System Settings → Accessibility → Display → Enable *Increase contrast*.

- [ ] **Night Shift**  
  System Settings → Displays → Night Shift → Schedule (e.g., Sunset to Sunrise).

---

## 2. Finder & File Handling

- [ ] **Show Filename Extensions**  
  Finder → Settings → Advanced → Enable *Show all filename extensions*.

- [ ] **Show Hidden Files**  
  Shortcut: `Cmd + Shift + .`  
  Permanent:  
  ```bash
  defaults write com.apple.finder AppleShowAllFiles -bool true
  killall Finder
  ```

- [ ] **Show Path Bar**  
  Finder → View → Show Path Bar.

- [ ] **Show Status Bar**  
  Finder → View → Show Status Bar.

- [ ] **Group Items by Kind**  
  Finder → View → Group By → Kind.

- [ ] **Sort Folders First**  
  Finder → Settings → Advanced → Enable *Keep folders on top*.

- [ ] **Customize Sidebar**  
  Finder → Settings → Sidebar → Add/remove useful locations.

- [ ] **Default Finder View (List/Column)**  
  Open Finder → View menu → Select preferred view → View → Show View Options → *Use as Defaults*.

- [ ] **Show Full POSIX Path in Title Bar**  
  ```bash
  defaults write com.apple.finder _FXShowPosixPathInTitle -bool true
  killall Finder
  ```

- [ ] **New Finder Windows → Home/Downloads**  
  Finder → Settings → General → *New Finder windows show* → Home/Downloads.

---

## 3. Input & Keyboard

- [ ] **Trackpad Speed**  
  System Settings → Trackpad → Adjust *Tracking speed*.

- [ ] **Tap to Click**  
  System Settings → Trackpad → Enable *Tap to click*.

- [ ] **Three-Finger Drag**  
  System Settings → Accessibility → Pointer Control → Trackpad Options → Enable *Three-Finger Drag*.

- [ ] **Natural Scrolling Toggle**  
  System Settings → Trackpad → Scroll & Zoom → Toggle *Natural scrolling*.

- [ ] **Keyboard Key Repeat Speed**  
  System Settings → Keyboard → Key Repeat → Fast  
  Delay Until Repeat → Short.

- [ ] **Disable Press-and-Hold Accents**  
  ```bash
  defaults write -g ApplePressAndHoldEnabled -bool false
  ```

- [ ] **Remap Keys**  
  - Caps Lock → Control (common dev choice).  
  - Caps Lock → Escape (alternative).  
  System Settings → Keyboard → Modifier Keys.

- [ ] **Keyboard Shortcuts / Window Management**  
  System Settings → Keyboard → Shortcuts → Customize.

- [ ] **Enable Full Keyboard Access**  
  System Settings → Keyboard → Keyboard Navigation → Enable *Use keyboard navigation to move focus*.

---

## 4. Security & Privacy

- [ ] **Enable FileVault**  
  System Settings → Privacy & Security → FileVault → Turn On.

- [ ] **Enable Firewall**  
  System Settings → Network → Firewall → Enable.

- [ ] **Disable Siri (optional)**  
  System Settings → Siri & Spotlight → Disable *Ask Siri*.

- [ ] **Disable Siri/Spotlight Suggestions (optional)**  
  System Settings → Siri & Spotlight → Turn off categories.

- [ ] **Touch ID for sudo (optional)**  
  Edit PAM config:  
  ```bash
  sudo nano /etc/pam.d/sudo
  ```  
  Add at the top:  
  ```
  auth sufficient pam_tid.so
  ```  

- [ ] **System Updates Auto-Check**  
  System Settings → General → Software Update → Enable *Automatically keep my Mac up to date*.

---

## 5. System Behavior & Performance

- [ ] **Faster Animations**  
  ```bash
  defaults write NSGlobalDomain NSWindowResizeTime -float 0.001
  defaults write com.apple.dock expose-animation-duration -float 0.1
  killall Dock
  ```

- [ ] **Mission Control Tweaks & Hotkeys**  
  System Settings → Desktop & Dock → Mission Control → Adjust.  
  System Settings → Keyboard → Shortcuts → Mission Control → Assign keys.

- [ ] **Screenshot Folder → ~/Screenshots**  
  ```bash
  mkdir ~/Screenshots
  defaults write com.apple.screencapture location ~/Screenshots
  killall SystemUIServer
  ```

- [ ] **Screenshot Format (PNG/JPG)**  
  ```bash
  defaults write com.apple.screencapture type jpg
  killall SystemUIServer
  ```

- [ ] **Disable Screenshot Shadow (optional)**  
  ```bash
  defaults write com.apple.screencapture disable-shadow -bool true
  killall SystemUIServer
  ```

---

## 6. Defaults / System Apps

- [ ] **Change Default Browser**  
  System Settings → Desktop & Dock → Default web browser.

- [ ] **Remove Unused Default Apps from Dock**  
  Drag icons out of Dock.

---

## ✅ Notes

- Items marked **optional** = personal preference (accessibility, Siri, screenshot shadows, etc.).  
- This list merges **blogs (Drouin, Wieruch, Rascia)** with **Master 2025 Checklist** into one reference.  
- Covers **system settings only**; apps and package managers are intentionally excluded.



---

## 1. Core Tools
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



---

## 2. Shell & Terminal
# macOS 2025 Developer Setup Checklist – Shell & Terminal Environment

This checklist focuses only on the **shell and terminal setup**,  
refined to use **iTerm2**, **Oh My Zsh**, and the **Dracula theme**.

---

## 2. Shell & Terminal Setup

- [ ] **Install iTerm2**  
  A better terminal emulator than the macOS default.  
  ```bash
  brew install --cask iterm2
  ```

- [ ] **Install Oh My Zsh**  
  A popular framework for managing Zsh configuration.  
  ```bash
  sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  ```

- [ ] **Enable Zsh Plugins**  
  Recommended plugins for productivity:  
  - `git` (default with Oh My Zsh)  
  - `zsh-autosuggestions`  
    ```bash
    brew install zsh-autosuggestions
    echo "source $(brew --prefix)/share/zsh-autosuggestions/zsh-autosuggestions.zsh" >> ~/.zshrc
    ```  
  - `zsh-syntax-highlighting`  
    ```bash
    brew install zsh-syntax-highlighting
    echo "source $(brew --prefix)/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ~/.zshrc
    ```

- [ ] **Install Dracula Theme for iTerm2**  
  1. Download theme:  
     ```bash
     git clone https://github.com/dracula/iterm.git ~/dracula-iterm
     ```  
  2. In iTerm2: Preferences → Profiles → Colors → Color Presets → Import.  
  3. Select **Dracula** as the active theme.

- [ ] **Set iTerm2 as Default Terminal**  
  iTerm2 → Preferences → General → *Make iTerm2 Default Term*.

- [ ] **Configure iTerm2 Preferences (optional)**  
  - Enable unlimited scrollback.  
  - Enable ⌘+number to switch tabs.  
  - Disable native full-screen mode for better tiling.  

---

## ✅ Notes

- Core workflow = **iTerm2 + Zsh (with Oh My Zsh) + Dracula theme**.  
- Plugins (`zsh-autosuggestions`, `zsh-syntax-highlighting`) improve usability.  
- Dracula ensures a consistent dark color scheme across tools.



---

## 3. Languages & Runtimes
# macOS 2025 Developer Setup Checklist – Languages & Runtimes

This checklist covers installation of programming languages and runtimes,  
focused only on **Node.js (via nvm)** and **Python**, ensuring the **latest stable versions** are installed.

---

## 3. Languages & Runtimes

### Node.js (via nvm)
- [ ] **Install nvm (Node Version Manager)**  
  ```bash
  brew install nvm
  mkdir ~/.nvm
  echo 'export NVM_DIR="$HOME/.nvm"' >> ~/.zshrc
  echo '[ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && . "/opt/homebrew/opt/nvm/nvm.sh"' >> ~/.zshrc
  source ~/.zshrc
  ```

- [ ] **Install Latest Node.js**  
  ```bash
  nvm install node       # Installs the latest stable version
  nvm use node
  nvm alias default node
  ```

- [ ] **Verify Node & npm**  
  ```bash
  node -v
  npm -v
  ```

- [ ] **Install Yarn (optional)**  
  ```bash
  npm install --global yarn
  ```

---

### Python
- [ ] **Install pyenv**  
  ```bash
  brew install pyenv
  ```

- [ ] **Add pyenv to Shell**  
  ```bash
  echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
  echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
  echo 'eval "$(pyenv init --path)"' >> ~/.zshrc
  source ~/.zshrc
  ```

- [ ] **Install Latest Python**  
  ```bash
  pyenv install $(pyenv install --list | grep -E "^[[:space:]]*[0-9]+\.[0-9]+\.[0-9]+$" | tail -1)
  pyenv global $(pyenv install --list | grep -E "^[[:space:]]*[0-9]+\.[0-9]+\.[0-9]+$" | tail -1)
  ```

- [ ] **Verify Python & pip**  
  ```bash
  python --version
  pip --version
  ```

---

## ✅ Notes

- **Node.js via nvm**: `nvm install node` always installs the latest stable version.  
- **Python via pyenv**: The `grep` and `tail` command ensures you always install the newest available version.  



---

## 4. Development Tools & IDEs
# macOS 2025 Developer Setup Checklist – Development Tools & IDEs

This checklist focuses on installing and configuring **VS Code**, **PyCharm**, and **Git** (with GitHub configuration).

---

## 4. Development Tools & IDEs

### Editors / IDEs

- [ ] **Install Visual Studio Code**
  ```bash
  brew install --cask visual-studio-code
  ```

- [ ] **Install PyCharm (Community Edition)**
  ```bash
  brew install --cask pycharm-ce
  ```

---

### Git & GitHub Configuration

- [ ] **Install Git**
  ```bash
  brew install git
  ```

- [ ] **Set Global Git Username & Email**
  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "your.email@example.com"
  ```

- [ ] **Enable Git Color Output**
  ```bash
  git config --global color.ui auto
  ```

- [ ] **Set Default Branch to main**
  ```bash
  git config --global init.defaultBranch main
  ```

- [ ] **Generate SSH Key for GitHub**
  ```bash
  ssh-keygen -t ed25519 -C "your.email@example.com"
  ```

- [ ] **Start SSH Agent and Add Key**
  ```bash
  eval "$(ssh-agent -s)"
  ssh-add --apple-use-keychain ~/.ssh/id_ed25519
  ```

- [ ] **Copy SSH Key to Clipboard**
  ```bash
  pbcopy < ~/.ssh/id_ed25519.pub
  ```
  Add this key to GitHub → Settings → SSH and GPG keys → *New SSH key*.

- [ ] **Test SSH Connection to GitHub**
  ```bash
  ssh -T git@github.com
  ```

- [ ] **Optional: Sign Commits with SSH**
  ```bash
  git config --global gpg.format ssh
  git config --global user.signingkey ~/.ssh/id_ed25519.pub
  git config --global commit.gpgsign true
  ```

- [ ] **Configure Useful Git Aliases**
  ```bash
  git config --global alias.co checkout
  git config --global alias.br branch
  git config --global alias.ci commit
  git config --global alias.st status
  git config --global alias.lg "log --oneline --graph --all --decorate"
  ```

---

## ✅ Notes

- **VS Code**: lightweight, extensible editor for all languages.  
- **PyCharm**: full IDE for Python development.  
- **GitHub setup** ensures you can push/pull securely via SSH.  
- Aliases save time for common Git commands (e.g., `git lg`).



---

## 5. Productivity & Communication
# macOS 2025 Developer Setup Checklist – Productivity & Communication

This checklist covers productivity, communication, and supporting tools for daily workflow.  
All items are tailored for macOS with install commands via Homebrew where available.

---

## Apps to Include

### Microsoft Office 365 Suite
- Includes Outlook, Word, Excel, PowerPoint.
- Install with Homebrew:
  ```bash
  brew install --cask microsoft-office
  ```

### Microsoft Teams
- Collaboration and communication.
  ```bash
  brew install --cask microsoft-teams
  ```

### Chrome (Browser)
- Main browser for development and daily use.
  ```bash
  brew install --cask google-chrome
  ```

### IINA (Media Player)
- Modern media player for macOS with wide codec support.
  ```bash
  brew install --cask iina
  ```

### XnView MP (Image Viewer/Manager)
- Versatile image viewer and manager.
  ```bash
  brew install --cask xnviewmp
  ```

### Spotify (Music Streaming)
- Music streaming for productivity.
  ```bash
  brew install --cask spotify
  ```

### Sublime Text (Notepad++ Alternative)
- Lightweight text editor, great for quick edits and coding.
  ```bash
  brew install --cask sublime-text
  ```

### Keka (Archiver Tool)
- Handles 7z, RAR, and other archive formats not supported by macOS Finder.
  ```bash
  brew install --cask keka
  ```

### Araxis Merge (Diff & Merge Tool)
- Professional diff and merge tool.
  ```bash
  brew install --cask araxis-merge
  ```

**Configure Araxis Merge for Git CLI**
```bash
git config --global merge.tool araxis
git config --global mergetool.araxis.path "/Applications/Araxis Merge.app/Contents/Utilities/compare"
git config --global mergetool.prompt false
```

**Configure Araxis Merge in Fork**
- Open **Fork → Preferences → Git**  
- Under **Merge Tool**, select **Custom**.  
- **Path:**  
  ```
  /Applications/Araxis Merge.app/Contents/Utilities/compare
  ```  
- **Arguments:**  
  ```
  $LOCAL $REMOTE $BASE $MERGED
  ```

### Fork (Git Client, SmartGit Alternative)
- Modern Git client with rich features.
  ```bash
  brew install --cask fork
  ```

### Double Commander (File Manager, Total Commander Alternative)
- Free, dual-pane file manager similar to Total Commander.
  ```bash
  brew install --cask double-commander
  ```

---

## ✅ Notes
- This section is focused purely on **productivity and communication apps**.  
- **Araxis Merge** is configured for both CLI Git and Fork integration.  
- **Double Commander** provides a Total Commander-like experience on macOS.  


---

## ✅ Notes
- Items are structured sequentially: do **#1 Core Tools first**, then move through #2–#5.  
- **System Settings (#0)** can be applied anytime.  
- All commands are tested on macOS 14/15 (Apple Silicon).  



---

## 🔁 Maintenance Notes
- Prefer **per-user runtimes** (nvm/pyenv) and **admin/system Brew** installs.
- When pinning versions becomes necessary (e.g., long-term reproducibility), add a **“Pinned Versions”** appendix with explicit versions and hashes.
- Consider generating a companion **install script** on each MINOR release to match the current checklist.
