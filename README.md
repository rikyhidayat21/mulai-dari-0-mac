# MacBook Air M4 – Programmer Daily Setup (Rails-Focused)

This repository documents my **clean, reproducible development environment setup** on a **MacBook Air M4 (Apple Silicon)**, optimized for **Ruby on Rails & web development**.

The goal of this setup is:
- Stability over hype
- One version manager for multiple languages
- Minimal shell hacks
- Easy onboarding for future machines

---

## System Requirements

- macOS (Apple Silicon)
- Fresh or clean environment recommended
- Zsh (default on macOS)

---

## 1. Xcode Command Line Tools

Required for:
- Git
- Compilers
- Native Ruby gems

```bash
xcode-select --install
```

> ⚠️ Important:  
> After installation finishes, **restart your Terminal** before continuing.

Verify:
```bash
git --version
```

---

## 2. Homebrew (Package Manager)

Install Homebrew:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Add Homebrew to PATH (Apple Silicon)

```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

Verify:
```bash
brew --version
```

---

## 3. Language Version Manager – mise

`mise` replaces:
- rbenv
- nvm
- asdf

### Install mise

```bash
brew install mise
```

### Activate mise (Zsh)

```bash
echo 'eval "$(mise activate zsh)"' >> ~/.zshrc
source ~/.zshrc
```

Verify:
```bash
mise --version
```

---

## 4. Ruby (Global Latest)

```bash
mise install ruby@latest
mise use ruby@latest --global
```

Verify:
```bash
ruby -v
which ruby
```

---

## 5. Node.js (LTS)

```bash
mise install node@lts
mise use node@lts --global
```

Verify:
```bash
node -v
npm -v
```

---

## 6. Browser

```bash
brew install --cask google-chrome
```

---

## 7. Window Management

```bash
brew install --cask rectangle
```

---

## 8. Spotlight Replacement

```bash
brew install --cask raycast
```

---

## 9. Terminal & Shell

```bash
brew install --cask iterm2
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

---

## 10. Neovim + LazyVim

```bash
brew install neovim
brew install --cask font-jetbrains-mono-nerd-font
git clone https://github.com/LazyVim/starter ~/.config/nvim
```

---

## 11. Code Editors

```bash
brew install --cask visual-studio-code
brew install --cask cursor
```

---

## 12. Optional – Backend Services

```bash
brew install postgresql@15
brew install mysql
brew install redis
brew install --cask docker
```

---

## Final Notes

This setup prioritizes stability, clarity, and long-term productivity.
