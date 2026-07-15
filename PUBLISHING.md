# Publishing

The local repository is ready to publish to GitHub.

Expected public repository:

```text
https://github.com/suyueyang1225-stack/awesome-data-quality-papers
```

## Option 1: GitHub Web UI

1. Open https://github.com/new
2. Repository name: `awesome-data-quality-papers`
3. Description: `Curated papers, tools, datasets, and research roadmap for data quality evaluation and improvement in AI systems.`
4. Visibility: Public
5. Do not initialize with README, .gitignore, or license.
6. Create repository.
7. Run:

```bash
cd /Users/suyy/Desktop/awesome-data-quality-papers
git push -u origin main
```

## Option 2: GitHub CLI

If `gh` is installed and authenticated:

```bash
cd /Users/suyy/Desktop/awesome-data-quality-papers
gh repo create suyueyang1225-stack/awesome-data-quality-papers \
  --public \
  --description "Curated papers, tools, datasets, and research roadmap for data quality evaluation and improvement in AI systems." \
  --source . \
  --remote origin \
  --push
```

