# Collaboration Bootcamp — survival guide series

One front door, several flavors of panic. A series of self-contained, single-file survival guides, served with GitHub Pages.

**Live site:** https://marianna3000.github.io/collaboration-bootcamp/

| Page | Path | Live URL |
|---|---|---|
| Hub (front door) | `index.html` | [/collaboration-bootcamp/](https://marianna3000.github.io/collaboration-bootcamp/) |
| `setup --survival-guide` | `setup-survival-guide/` | [/setup-survival-guide/](https://marianna3000.github.io/collaboration-bootcamp/setup-survival-guide/) |
| `git --survival-guide` | `git-survival-guide/` | [/git-survival-guide/](https://marianna3000.github.io/collaboration-bootcamp/git-survival-guide/) |
| `ci --survival-guide` | `ci-survival-guide/` | [/ci-survival-guide/](https://marianna3000.github.io/collaboration-bootcamp/ci-survival-guide/) |
| `spark --survival-guide` | `spark-survival-guide/` | [/spark-survival-guide/](https://marianna3000.github.io/collaboration-bootcamp/spark-survival-guide/) |
| `python --survival-guide` | `python-survival-guide/` | [/python-survival-guide/](https://marianna3000.github.io/collaboration-bootcamp/python-survival-guide/) |
| `ai --survival-guide` (WIP) | `ai-survival-guide/` | [/ai-survival-guide/](https://marianna3000.github.io/collaboration-bootcamp/ai-survival-guide/) |

## How it works

- Each guide is **one self-contained `index.html`** — no build step, no dependencies, no framework. Edit the file, push, done.
- GitHub Pages deploys from the `main` branch, root folder. Every push to `main` goes live automatically within ~1 minute (check the **Actions** tab for the `pages build and deployment` run).
- Cross-page links are root-relative (`/collaboration-bootcamp/git-survival-guide/`), so they only resolve on the deployed site — see *Previewing locally* below.

## Access

- The repo is **public** (required for Pages on a free account): anyone can read, clone, and open issues or PRs.
- **Push access** is limited to collaborators. To grant it: repo **Settings → Collaborators → Add people** (they get an email invite to accept).
- No write access? Fork the repo, make your change, and open a pull request — that's the front door for external contributions.

## Contributing a change

```bash
git clone https://github.com/marianna3000/collaboration-bootcamp.git
cd collaboration-bootcamp
git switch -c fix/typo-in-git-guide   # never work on main — the git guide says so itself
# ...edit the relevant index.html...
git add -p && git commit -m "Fix typo in git guide SOS section"
git push
# then open a PR on GitHub
```

Small PRs, reviewable in one coffee. Direct pushes to `main` deploy immediately — fine for typos if you have access, but anything structural should go through a PR.

## Previewing locally

Open the `index.html` directly in a browser, or serve the repo:

```bash
python -m http.server 8000
# → http://localhost:8000/
```

Note: cross-page links between guides assume the `/collaboration-bootcamp/` path prefix and will 404 locally. Each page renders fully on its own; only the inter-guide navigation needs the live site.

## Adding a new module

1. Create a folder (slug becomes the URL): `spark-survival-guide/index.html` — self-contained, zero external build.
2. Follow the series constants (documented on the hub page): mono headings, serif body, a day-zero loop, a mental model, wanted posters, a settled holy war, an SOS chapter with a panic button, and a boss fight.
3. Use root-relative links for cross-references: `/collaboration-bootcamp/<slug>/`.
4. Update the hub `index.html`: edit the module's card from ⏳/◌ to ● live and wire up its links.
5. Push. Pages handles the rest — no configuration needed for new folders.

## Conventions

- Imperative, ≤50-char commit subjects (the git guide is watching).
- One logical change per commit; `git add -p` is your scalpel.
