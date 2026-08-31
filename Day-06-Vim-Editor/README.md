# 🚀 Day 6 — VIM Editor

## 📚 Topic
- VIM Eitor
  
## 📖 What I Learned
## What is VIM?
- **Vim** = **Vi IMproved** editor (an improved version of the older `vi` editor)
- Command to open: `vim <filename>`
- **Default mode** when Vim opens = **Esc (Command) Mode**

## File Behavior
- If the file already exists → Vim **opens** it
- If the file does **not** exist → Vim will **create and open** it
- To write/insert content into the file → press `i` (Insert Mode)

## Vim Modes and How to Switch Between Them

```
                ┌───────────┐
        :  ┌────┤  Esc Mode ├────┐  i
           │    └─────┬─────┘    │
           ▼        ▲     ▲      ▼
      ┌─────────┐   │     │  ┌─────────┐
      │ : Mode  ├───┘     └──┤ i Mode  │
      └─────────┘  esc  esc  └─────────┘
       (Colon)              (Insert)
```

## 💻 Commands Used

- **Esc Mode** → press `i` → **Insert Mode**
- **Esc Mode** → press `:` → **Command/Colon Mode**
- From **Insert Mode** or **Colon Mode** → press `Esc` → back to **Esc Mode**

## Insert Mode Commands `[i]`

| Command | Meaning |
|---|---|
| `:wq` | **Write + Quit** — saves changes and exits the editor (`Esc + : + wq`) |
| `:q!` | Exits the editor **without saving** changes (`Esc + : + q!`) |
| `:q` | Exits **only if no changes** have been made (`Esc + : + q`) |

## Line Number Commands
| Command | Meaning |
|---|---|
| `:set nu` | Displays line numbers next to text |
| `:set nonu` | Hides line numbers |
| `:number` | Displays the cursor's current line number |

## Search Commands
| Command | Meaning |
|---|---|
| `:/<word>` | Searches for a word from **top to bottom** |
| `:?<word>` | Searches for a word from **bottom to top** |
| `:noh` | Clears search highlighting |

## Delete & Replace (Substitution) Commands
| Command | Meaning |
|---|---|
| `:<line number>d` | Deletes the specified line |
| `:<line>s/word/newword` | Replaces the **first occurrence** of `word` with `newword` on that line (`s` = substitution) |
| `:<line>s/word/newword/g` | Replaces **all occurrences** on that line (`g` = global) |
| `:%s/word/newword/g` | Replaces **all occurrences of the word in the entire file** |

## Escape Mode Commands `[esc]`
| Command | Meaning |
|---|---|
| `gg` | Navigates to the **top / first line** of the file |
| `Shift + g` (`G`) | Navigates to the **bottom / last line** of the file |
| `u` | **Undo** the last action |
| `Ctrl + r` | **Redo** the undone action |
| `dd` | **Deletes** the current line |
| `yy` | **Copies (yanks)** the current line |
| `p` | **Pastes** copied/cut text **after** the cursor / below the current line |
| `Shift + p` (`P`) | **Pastes** copied/cut text **on top** of / **above** the cursor line |

---

## ✅ Output Screenshots
<img width="1920" height="1080" alt="Screenshot 2026-08-31 184951" src="https://github.com/user-attachments/assets/205c2128-3fb7-4df0-8f11-a597727dcf3f" />
<img width="1920" height="1080" alt="Screenshot 2026-08-31 192827" src="https://github.com/user-attachments/assets/fa25bef4-8431-4c6f-a5ab-6eee38af2570" />

### 🎯 Quick Recap
- Vim has 3 modes: **Esc (Command)**, **Insert (`i`)**, **Colon (`:`)**
- `:wq` save & quit | `:q!` quit without saving | `:q` quit if unchanged
- `dd`/`yy`/`p` = cut/copy/paste a line
- `gg`/`G` = jump to top/bottom of file
- `u`/`Ctrl+r` = undo/redo
