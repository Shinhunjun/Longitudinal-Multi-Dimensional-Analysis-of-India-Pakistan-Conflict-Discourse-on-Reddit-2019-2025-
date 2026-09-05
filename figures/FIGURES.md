# Figure manifest

Nine figure slots are planned in `appendix/appendix.tex` (Appendix H, Table
`tab:figureplan`). Seven source files are copied into this directory; two slots
have no source yet.

`\graphicspath{{figures/}}` is set in `preamble/00_documentclass.tex`, so a
section file refers to a figure by bare stem:

```latex
\begin{figure}[t]
  \centering
  \includegraphics[width=\linewidth]{r5_ame_plot}
  \caption{...}
  \Description{Plain-text description, under 2,000 characters. Required by ACM.}
  \label{fig:ame}
\end{figure}
```

## Slot status

| Slot | Content | File in this directory | Source in repo | Status |
|---|---|---|---|---|
| Fig 1 | Annotation-layer architecture with gating | — | `methodology/analytical_roadmap.md:31-66` (mermaid) | **build as vector** |
| Fig 2 | Labeller comparison: κ by layer × labeller family, human ceiling marked | — | §3.7 / `tables/tab_commercial.tex`, `tables/tab_opensource.tex` | **build — carries C2** |
| Fig 3 | Crisis-signature cosine forest with CIs | `r1r2_cosine_forest.png` | `Report/Week11/figures/` | ready |
| Fig 4 | Parent-to-child transition matrices | `r1r2_transition_heatmaps.png` | `Report/Week11/figures/` | trim 7 panels to 3 |
| Fig 5 | AME gaps on P(Neg)/P(Pos) with KTW CIs | `r5_ame_plot.png` | `Report/Week3/figures/` | ready — most important figure |
| Fig 6 | Punishment forest + raiding signature | `r6_punishment_forest.png`, `r6_raiding_signature.png` | `Report/Week3/figures/` | combine into one 2-panel figure |
| Fig 7 | Controversiality by frame + tone-independence inset | `r8_frame_effect.png` | `Report/Week3/figures/` | see note below |
| Fig 8 | CRV1 versus WCB p-values, all 42 estimates | — | — | **build — carries C3** |
| Fig 9 | Specification curve, 36 cells | `r1r2_spec_curve.png` | `Report/Week11/figures/` | ready |

## Notes carried over from the outline

- **Prefer the `Report/Week11/figures/r1r2_*` set** over `Report/Week1` and
  `Report/Week2`. The earlier sets carry pre-remediation numbers.
- **Fig 7 status conflict.** Table `tab:figureplan` records
  `r8_frame_effect.png` as "does not exist — generate", but the file is present
  at `Report/Week3/figures/r8_frame_effect.png` and has been copied here.
  Confirm it renders the intended quantity before trusting the copy; if it does,
  correct the status cell in `tables/tab_figureplan.tex`.
- **Blocker — figure fix.** `r1r2_annotation_audit.png` is *not* copied here.
  Its suptitle is hard-coded at `notebooks/lib/r1r2_figures.py:482-483` as
  "Annotation substrate — no human inter-annotator agreement exists for any
  layer", which the 2026-08-02 annotation-validation pass made false. Regenerate
  before using it anywhere in the paper.
- **Accessibility.** Colourblind-safe palettes and non-colour redundant
  encoding throughout. Every figure needs a `\Description{}` under 2,000
  characters, per ACM policy. Open author-side item A5 is confirmation that the
  existing figures already satisfy the palette requirement.
- **Vector over raster.** For Overleaf, prefer PDF or vector-native output for
  Figs 1, 2 and 8 when they are built. The seven copied files are PNG because
  that is what the notebooks emit.
