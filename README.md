# reedline (AI-patched fork)

> [!NOTE]
> **This is a personal fork patched using AI** to fit personal needs, modal editing workflow, and custom keybindings modeled after the [Helix editor](https://helix-editor.com/).
>
> Official upstream project: **[nushell/reedline](https://github.com/nushell/reedline)**.

---

## Why this fork exists

This repository contains modifications developed with AI assistance to support a tailored [Helix](https://helix-editor.com/)-style editing experience directly in the line editor powering [Nushell](https://github.com/nushell/nushell), alongside instance-isolated SQLite history.

## What was changed

1. **Helix Keybindings & Modal Editing**:
   - **`gh` / `gl` / `gs` / `ge` / `gg`**: Jump to line start (`gh`), line end (`gl`), first non-blank (`gs`), line end (`ge`), and buffer start (`gg`). Uppercase `G...` extends selection.
   - **Selection motions `H` and `L`**: Select to first non-blank character (`H`) or line end (`L`).
   - **Line selection `x` and `V`**: `x` selects the line; `V` expands selection across line edges.
   - **Buffer selection `%`**: Selects the entire buffer.
   - **Selection collapse `;`**: Semicolon collapses any active selection back to a single cursor and returns to Normal mode.
   - **Cursor/Anchor swap `Alt-;`**: Swaps cursor and anchor position.
   - **Quick line deletion `Ctrl-d`**: Deletes the entire current line (matching Helix `@xd`).
   - **Text Object Selection (`SelectTextObject`)**: Added `EditCommand::SelectTextObject` to allow selecting text objects (`word`, `bigword`, `brackets`, `quote`) directly without requiring deletion/copying (e.g. Helix `@miw` / `@miW`).
   - **Insert mode navigation**: `Alt-h` (left), `Alt-l` (right), `Alt-j` (open line below), `Alt-k` (open line above).
   - **Word navigation**: `b` / `B` (backward word/bigword start), `e` / `E` (forward word/bigword end), `w` / `W` (forward word/bigword start or word selection).

2. **Upstream Compatibility**:
   - Fully passes the entire Reedline test suite (1,665 unit and integration tests).

---

For documentation on the original library, please refer to upstream [nushell/reedline](https://github.com/nushell/reedline).
