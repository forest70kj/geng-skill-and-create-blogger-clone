# GitHub Upload Instructions

## Option 1：GitHub Web Upload

1. Create a new GitHub repository.
2. Upload the contents of this folder:
   ```text
   github_release/geng-skill-and-create-blogger-clone/
   ```
3. Keep the repository public if you want open source.
4. Use MIT License.

## Option 2：Git Remote Push

After creating a GitHub repository, run:

```bash
cd github_release/geng-skill-and-create-blogger-clone
git remote add origin git@github.com:<YOUR_USERNAME>/<YOUR_REPO>.git
git branch -M main
git push -u origin main
```

Do not push before reviewing `PUBLIC_RELEASE_SENSITIVE_SCAN.md`.
