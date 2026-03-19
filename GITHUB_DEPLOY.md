# Deploy This Project To GitHub

This folder was initialized as a local Git repository.

## 1) Create a new empty repo on GitHub

Create a repository on GitHub web UI (for example: `Hyper-Alpha-Arena-main`), and do not add README/LICENSE/.gitignore in that new repo.

## 2) Set local branch to `main`

```bash
git branch -M main
```

## 3) Commit code locally

```bash
git add .
git commit -m "chore: initial import and github ci"
```

## 4) Connect and push to your GitHub repo

Replace `<YOUR_REPO_URL>` with your repository HTTPS or SSH URL.

```bash
git remote add origin <YOUR_REPO_URL>
git push -u origin main
```

## 5) Verify GitHub Actions

After push, open:

`GitHub Repo -> Actions -> CI`

The workflow checks:
- Frontend build (`pnpm --dir frontend build`)
- Backend syntax compile (`python -m compileall backend`)

## Optional: protect `main`

In GitHub:
`Settings -> Branches -> Add branch protection rule -> main`

Recommended:
- Require a pull request before merging
- Require status checks to pass (`CI`)
