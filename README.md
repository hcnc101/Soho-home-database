## Soho Home Database

This repository is set up to store and version your CSV database.

### How to use
- Place your CSV files in the `data/` directory.
- Avoid committing very large files (>100 MB) unless using Git LFS (configured below for `*.csv`).
- Use the commands in the section below to initialize the repo locally and push to GitHub.

### Repository structure
```
data/          # Put your CSV files here
README.md      # This guide
.gitignore     # Files to ignore
.gitattributes # Git LFS for large CSVs
```

### Add your CSV
1. Copy your CSV file(s) into the `data/` folder.
2. (Optional) If a CSV is very large (>100 MB), Git LFS will handle it automatically.
3. If you want to preview or clean your CSVs, you can use spreadsheet tools or Python/R notebooks locally—no tooling is required in this repo.

### Initialize locally and push to GitHub
Follow these steps in your terminal after you add your CSVs:

```bash
# From the repo root
git init
git lfs install
git add .
git commit -m "Initial commit: add data and repo scaffold"

# Create a new GitHub repo (via website or gh CLI), then set origin:
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo>.git
git push -u origin main
```

If you have the GitHub CLI installed, you can create and push in one go:

```bash
gh repo create <your-repo> --public --source=. --remote=origin --push
```

### Notes
- Git LFS is configured for `*.csv` to avoid large-file issues. Install LFS once with:

```bash
git lfs install
```

After that, future clones will fetch large files correctly.


