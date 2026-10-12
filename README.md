<p align="center">
  <img src="resources/logo.png" width="120" alt="Akkhar Code Patcher Logo" />
</p>

<h1 align="center">Akkhar Code Patcher</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Unmaintained-lightgrey?style=for-the-badge" alt="Status: Unmaintained" />
  <img src="https://img.shields.io/badge/Successor-Brud%20Code-FF6F00?style=for-the-badge" alt="Successor: Brud Code" />
  <img src="https://img.shields.io/badge/VS%20Code-1.80%2B-blue?style=for-the-badge&logo=visualstudiocode&logoColor=white" alt="VS Code 1.80+" />
  <img src="https://img.shields.io/badge/License-ALPL-4CAF50?style=for-the-badge" alt="License ALPL" />
</p>

> [!IMPORTANT]
> **This project is no longer maintained.** Development continues in
> **[Brud Code](https://github.com/rahatarch/brud)**, a deterministic execution engine that lets any AI chatbot
> safely edit real codebases — every change reviewed, logged, and reversible.
> Install it from the [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=akkhar-labs.brud).
>
> This repository is kept for history. Issues and pull requests are no longer reviewed.

---

## What it was

Akkhar Code Patcher was a VS Code extension for applying small, targeted
search-and-replace patches produced by AI chatbots, instead of copy-pasting
whole regenerated files.

It was the first step in a line of work that evolved into *Sover* and then into
**Brud Code**, also known as "Akkhar-Code" in the ASM reference integration.

## Why I built it

I was building [Truck Pai](https://truckpai.com) with free AI chatbots and no
budget for paid AI coding tools. Every small change meant the AI regenerated an
entire file, and pasting it back often introduced formatting problems or
unintended edits. I wanted a way to paste only the change, preview it, and apply
it safely.

## Features

- **Preview before applying:** side-by-side diff of every change.
- **Atomic undo:** all edits from one patch revert with a single undo.
- **Indentation repair:** normalises indentation from AI output.
- **Works with any AI:** web chatbots, APIs, or local models — anything that can
  emit the patch format.
- **Bottom-to-top execution:** edits are applied from the end of the file
  upward so line positions stay valid.

## Patch format

```
File Path: src/utils.js
<<<<<<< SEARCH [0]
function calculateTotal(price, tax) {
  return price + tax;
}
=======
function calculateTotal(price, tax, discount = 0) {
  return price + tax - discount;
}
>>>>>>> REPLACE [0]
```

Paste the block into the sidebar → **Preview Bulk Diff** → **Execute Patch**.

## Lineage

**Akkhar Code Patcher → Sover → [Brud Code](https://github.com/rahatarch/brud)**

Brud Code adds a standalone microkernel, snapshot history with revert/restore,
workspace sandboxing, a terminal engine, and CI-tested protocol handling.

---

<p align="center">
  Built in Bogura, Bangladesh by <a href="https://github.com/rahatarch">Rahat Hasan</a><br />
  <sub>© 2026 Akkhar-Labs</sub>
</p>
