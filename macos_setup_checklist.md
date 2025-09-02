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

