# Release Process

## 1. Make your changes

Edit the relevant files (e.g., `php-extensions.txt` to add/remove extensions).

## 2. Commit and push to main

```bash
git add .
git commit -m "Description of changes"
git pull --rebase origin main
git push origin main
```

## 3. Create a GitHub release

This will create a tag and trigger the build workflow:

```bash
gh release create X.Y.Z --title "X.Y.Z" --notes "Description of changes"
```

## 4. Wait for the build workflow

The `Build PHP` workflow will automatically start. Check its status:

```bash
gh run list --workflow=build-php.yml --limit 1
```

Watch the run (optional):

```bash
gh run watch <run-id>
```

## 5. Wait for 4 PRs

The workflow creates 4 PRs, one for each platform:
- linux arm64
- linux x64
- mac arm64
- mac x64

Check for open PRs:

```bash
gh pr list --state open
```

## 6. Merge all PRs

```bash
gh pr merge <pr-number> --merge --delete-branch
```

Or merge all at once:

```bash
gh pr list --state open --json number --jq '.[].number' | xargs -I {} gh pr merge {} --merge --delete-branch
```
