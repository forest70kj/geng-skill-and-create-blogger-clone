# GitHub Upload Instructions / GitHub 上传说明

## Option 1：GitHub Web Upload / 网页上传

1. Create a new GitHub repository. / 新建一个 GitHub 仓库。
2. Upload the contents of this folder. / 上传这个文件夹里的内容：
   ```text
   github_release/geng-skill-and-create-blogger-clone/
   ```
3. Keep the repository public if you want open source. / 如果想开源，就把仓库设为 public。
4. Use MIT License. / 使用 MIT License。

## Option 2：Git Remote Push / 命令行推送

After creating a GitHub repository, run:

新建 GitHub 仓库后，运行：

```bash
cd github_release/geng-skill-and-create-blogger-clone
git remote add origin git@github.com:<YOUR_USERNAME>/<YOUR_REPO>.git
git branch -M main
git push -u origin main
```

Do not push before reviewing `PUBLIC_RELEASE_SENSITIVE_SCAN.md`.

推送前先看 `PUBLIC_RELEASE_SENSITIVE_SCAN.md`。

After upload, confirm that the `skills/` directory appears at the repository root.

上传后，确认仓库根目录能看到 `skills/` 文件夹。
