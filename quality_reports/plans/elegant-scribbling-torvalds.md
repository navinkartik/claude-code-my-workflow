# Plan: Adapt Workflow Configuration for Signaling Waste

**Status:** APPROVED
**Date:** 2026-03-27
**Task:** Configure Claude Code academic workflow for the "Signaling Waste" research paper

---

## Context

- **Paper:** "How Wasteful is Signaling?"
- **Authors:** Alex Frankel (Chicago Booth) & Navin Kartik (Yale)
- **Type:** Economic theory paper, aimed at top econ journal
- **Deliverable:** Paper only (.tex) — maintained on Overleaf
- **Bibliography:** `FK-dissipation.bib`
- **Main file:** `main.tex` (already in repo)
- **LaTeX engine:** pdflatex
- **Coauthor comments:** Document `\navin{}` and `\alex{}` for Claude to help manage
- **Autonomy level:** Check-in frequently (learning mode)

---

## Files to Modify

### 1. CLAUDE.md (major update)

Replace all placeholders with project-specific values:

| Section | Current | New Value |
|---------|---------|-----------|
| Line 8 | `[YOUR PROJECT NAME]` | Signaling Waste |
| Line 9 | `[YOUR INSTITUTION]` | Yale University |
| Line 27 | `[YOUR-PROJECT]` | SignalingWaste |
| Line 30 | `Bibliography_base.bib` | `FK-dissipation.bib` |

**Additional changes:**
- Update folder structure to reflect paper-only workflow (remove Slides/, Quarto/ emphasis)
- Replace Beamer/Quarto environment tables with LaTeX theorem environments from `main.tex`
- Add notation registry for the paper's key symbols
- Update "Current Project State" to show paper sections instead of lectures
- Adjust commands section for paper compilation (pdflatex vs xelatex, bibtex)

### 2. domain-reviewer.md (customize for econ theory)

Adapt the 5 review lenses for game-theoretic signaling papers:

| Lens | Customization |
|------|---------------|
| 1: Assumption Stress Test | Add signaling-specific checks: single-crossing, boundary conditions, belief consistency |
| 2: Derivation Verification | Add: equilibrium characterization ODEs, comparative statics signs, envelope conditions |
| 3: Citation Fidelity | Focus on signaling literature (Spence, Riley, Mailath, etc.) |
| 4: Code-Theory Alignment | Mark as optional (paper-only, no code) |
| 5: Backward Logic Check | Adapt for paper sections vs slides |

Update persona from "top-journal referee for lectures" to "Econometrica/AER referee for theory papers"

### 3. Bibliography_base.bib

- Either delete (unused) or symlink to FK-dissipation.bib
- Update CLAUDE.md to reference correct bib file

### 4. Session log update

Add notation registry and key decisions to session log

---

## Key Notation to Document

From `main.tex` lines 110-132:

| Symbol | Meaning | LaTeX |
|--------|---------|-------|
| `\R`, `\Rpos`, `\Rstrpos` | Reals, non-negative, strictly positive | `\mathbb{R}`, subscripts |
| `\E`, `\Prob` | Expectation, probability | `\mathbb{E}`, `\mathbb{P}` |
| `\theta`, `\typemin`, `\typemax` | Type, bounds (0, ̄θ) | `\theta`, `0`, `\overline\theta` |
| `\beta`, `\sigma` | Benefit elasticity, strain elasticity | - |
| `\elaB`, `\elaS`, `\elaR` | Type-dependent elasticities | `\tilde\beta`, `\tilde\sigma`, `\tilde\rho` |
| `V(\cdot)`, `C(\cdot,\cdot)` | Benefit function, cost function | - |
| `A(\theta)` | Equilibrium signaling action | - |
| `W` | Waste ratio | - |

---

## LaTeX Theorem Environments

From `main.tex` lines 77-103:

| Environment | Style | Use |
|-------------|-------|-----|
| `theorem`, `lemma`, `claim`, `proposition`, `conjecture`, `corollary`, `assumption`, `observation`, `condition` | plain | Main results |
| `remark`, `fact` | remark | Side notes |
| `example`, `definition` | definition | Examples end with ◇ |

---

## Skills Relevance Assessment

**Highly relevant for this project:**
- `/review-paper` — manuscript review (structure, objections)
- `/validate-bib` — citation cross-reference
- `/commit` — git workflow
- `/proofread` — grammar/typos in paper

**Less relevant (paper-only, no slides):**
- `/compile-latex`, `/deploy`, `/extract-tikz`, `/translate-to-quarto`, `/qa-quarto`, `/visual-audit`, `/pedagogy-review`, `/slide-excellence`

**May be useful later:**
- `/lit-review` — literature synthesis
- `/research-ideation` — research extensions

---

## Verification Steps

1. After editing CLAUDE.md: Read it back, confirm no placeholders remain
2. After editing domain-reviewer.md: Confirm persona and lenses are appropriate
3. Test compilation: `pdflatex main.tex && bibtex main && pdflatex main.tex && pdflatex main.tex`
4. Confirm git status is clean and changes are committable

---

## User Decisions (Confirmed)

1. **Compilation engine:** pdflatex
2. **Coauthor comments:** Yes, document `\navin{}` and `\alex{}` for Claude to help manage
3. **Autonomy:** Check-in frequently during initial sessions

---

## Implementation Order

1. Update CLAUDE.md with project metadata and notation
2. Customize domain-reviewer.md for econ theory
3. Update session log with decisions
4. Verify configuration works
5. Commit changes (if requested)
