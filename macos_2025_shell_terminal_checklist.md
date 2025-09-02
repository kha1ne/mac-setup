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

