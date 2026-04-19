Deploy VEGA Terminal to GitHub Pages.

Steps:
1. Confirm working tree is clean: `git status`
2. If there are uncommitted changes, ask the user before proceeding
3. Push to main: `git push origin main`
4. GitHub Pages will automatically deploy from the root of the main branch
5. Live URL will be: https://<username>.github.io/<repo-name>/

Prerequisites:
- GitHub Pages must be enabled in repo Settings → Pages → Source: main branch / root
- The `index.html` file must be in the root (it is — this is a single-file project)
