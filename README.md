# jetbrain

Local workspace for msis / DEV tickets (Jira: `blakeh1business.atlassian.net`).

## Git + Jira

After this repo is on GitHub, connect it in Jira: **Project → Code → Connect repository**.  
Use issue keys in commits, e.g. `DEV-2 your message`.

## Source control (Git)

Repo: `https://github.com/harriibb/jetbrain.git`  
These commands work in **Terminal**, **Git Bash** (Windows), or your IDE’s integrated terminal. Run them from the project folder.

### Everyday: save work and upload

```bash
cd /path/to/jetbrain
git status
git add .
git commit -m "DEV-2 short description"
git push
```

Stage one file only: `git add index.html`

### Get latest from GitHub

```bash
git fetch origin
git checkout main
git pull --rebase origin main
```

If pull complains about **uncommitted changes**, either commit them first, or temporarily set them aside:

```bash
git stash -u
git pull --rebase origin main
git stash pop
```

### Match GitHub exactly (discard local edits)

**One file** (e.g. back to what’s on `main`):

```bash
git fetch origin
git restore --source=origin/main --staged --worktree index.html
```

**Whole repo** (destructive — loses all uncommitted and unpushed local commits on this branch):

```bash
git fetch origin
git checkout main
git reset --hard origin/main
```

### Useful checks

```bash
git status              # what changed, which branch
git log -3 --oneline    # recent commits
git remote -v           # where origin points
```

### First-time clone (another machine)

```bash
git clone https://github.com/harriibb/jetbrain.git
cd jetbrain
```

### One-time identity (if Git asks who you are)

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```
