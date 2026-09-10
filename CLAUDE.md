# Personal Website Assistant Guide

This repository is Davi Moreira's Quarto personal website, published from the
tracked `docs/` directory at `https://davi-moreira.github.io/`.

## Working conventions

- Treat the root `.qmd` files, `_quarto.yml`, CSS files, includes, and source
  assets as the editable sources. Treat `docs/` as generated output.
- Preserve the site structure and analytics configuration in `_quarto.yml`
  unless the task explicitly changes them.
- After a source-content or styling change, render the full site with:

  ```bash
  /Applications/RStudio.app/Contents/Resources/app/quarto/bin/quarto render
  ```

- Inspect `git status` and the relevant source/output diff before committing.
  Stage specific files rather than using `git add .`.
- For a requested published website change, commit the source and rendered
  `docs/` output and push `main` to `origin`.
- Do not commit secrets, private source material, temporary files, or local R
  state.

## Agent compatibility

These instructions are shared by Claude Code and Codex. Agent-specific tool
names should be mapped to the equivalent available tool, while literal paths,
filenames, commands, and configuration names remain unchanged.
