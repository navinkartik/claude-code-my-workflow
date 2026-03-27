# CLAUDE.MD -- Signaling Waste Research Paper

**Project:** Signaling Waste ("How Wasteful is Signaling?")
**Authors:** Alex Frankel (Chicago Booth) & Navin Kartik (Yale)
**Branch:** main
**Primary:** Overleaf (copy-paste workflow with this repo)

---

## Core Principles

- **Plan first** -- enter plan mode before non-trivial tasks; save plans to `quality_reports/plans/`
- **Verify after** -- compile and confirm output at the end of every task
- **Precision over speed** -- this is a top-journal theory paper; rigor matters
- **Quality gates** -- nothing ships below 80/100
- **[LEARN] tags** -- when corrected, save `[LEARN:category] wrong → right` to MEMORY.md
- **Check-in frequently** -- during initial sessions, pause after major steps

---

## Folder Structure

```
SignalingWaste/
├── CLAUDE.MD                    # This file (loaded every session)
├── main.tex                     # Main paper file
├── FK-dissipation.bib           # Bibliography
├── .claude/                     # Rules, skills, agents, hooks
├── Figures/                     # Figures and TikZ diagrams
├── quality_reports/             # Plans, session logs, merge reports
├── explorations/                # Research sandbox (see rules)
├── templates/                   # Session log, quality report templates
└── master_supporting_docs/      # Reference papers
```

---

## Commands

```bash
# LaTeX compilation (3-pass, pdflatex)
pdflatex -interaction=nonstopmode main.tex
bibtex main
pdflatex -interaction=nonstopmode main.tex
pdflatex -interaction=nonstopmode main.tex

# Quality score (for auxiliary files if created)
python scripts/quality_score.py [file]
```

---

## Quality Thresholds

| Score | Gate | Meaning |
|-------|------|---------|
| 80 | Commit | Good enough to save |
| 90 | PR | Ready for coauthor review |
| 95 | Excellence | Submission-ready |

---

## Skills Quick Reference (Most Relevant)

| Command | What It Does |
|---------|-------------|
| `/review-paper [file]` | Manuscript review (structure, econometrics, objections) |
| `/validate-bib` | Cross-reference citations |
| `/proofread [file]` | Grammar/typo review |
| `/commit [msg]` | Stage, commit, PR, merge |
| `/lit-review [topic]` | Literature search + synthesis |
| `/research-ideation [topic]` | Research questions + strategies |
| `/context-status` | Show session health + context usage |
| `/deep-audit` | Repository-wide consistency audit |

---

## LaTeX Theorem Environments

| Environment | Style | Use |
|-------------|-------|-----|
| `theorem` | plain | Major results |
| `proposition` | plain | Key propositions |
| `lemma`, `claim` | plain | Supporting results |
| `corollary` | plain | Consequences |
| `assumption`, `condition` | plain | Model assumptions |
| `remark`, `fact` | remark | Side notes |
| `example` | definition | Examples (ends with ◇) |
| `definition` | definition | Formal definitions |

---

## Key Notation

| Symbol | Meaning | LaTeX |
|--------|---------|-------|
| θ ∈ [0, θ̄) | Agent type | `\theta`, `\typemin`, `\typemax` |
| V(θ̂) | Benefit from perception θ̂ | `V(\hat\theta)` |
| C(a, θ) | Cost of action a for type θ | `C(a, \theta)` |
| A(θ) | Equilibrium signaling action | `A(\theta)` |
| β | Benefit elasticity | `\beta` |
| σ | Strain elasticity (cost advantage) | `\sigma` |
| W = β/(β+σ) | Waste ratio | `W` |
| β̃, σ̃, ρ̃ | Type-dependent elasticities | `\elaB`, `\elaS`, `\elaR` |
| ℝ, ℝ₊, ℝ₊₊ | Reals, non-negative, positive | `\R`, `\Rpos`, `\Rstrpos` |
| 𝔼, ℙ | Expectation, probability | `\E`, `\Prob` |

---

## Coauthor Comment Macros

| Command | Renders | Use |
|---------|---------|-----|
| `\navin{text}` | Violet: [NK: *text*] | Navin's comments |
| `\alex{text}` | Blue: [AF: *text*] | Alex's comments |
| `\redt{text}` | Red text | Emphasis/attention |
| `\bluet{text}` | Blue text | Emphasis/attention |

When helping with comments: summarize outstanding `\navin{}` and `\alex{}` items, help resolve discussions.

---

## Current Paper Structure

| Section | Status | Key Content |
|---------|--------|-------------|
| 1. Introduction | Draft | Motivation, waste ratio formula, roadmap |
| 2. Model | Draft | Type space, signaling game, equilibrium definition |
| 3. Results | Draft | Constant waste theorem, characterization, comparative statics |
| 4. Welfare | Draft | Social value of information, pooling vs separation |
| 5. Tournament | Draft | Winner-take-all signaling, Tullock connection |
| 6. Conclusion | Draft | Implications, limitations |
| Appendix | Draft | Proofs, technical details |
