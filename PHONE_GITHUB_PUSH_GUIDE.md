# Phone + GitHub Web: How to publish your local Codex edits

If you are using only the GitHub website on your phone, there is **no setting** that lets GitHub run shell commands in this local Codex workspace automatically.

## If your screen looks like “Conversation / Diff / Logs”
That view means you are inside the Codex task page. On many phones, the local file tree is hidden/collapsed.

Try this exact flow:
1. Tap **Diff** first (next to Conversation) to see changed files.
2. Open the changed file (for example `index.html`) from the diff file list.
3. In the file view, use the browser/file menu to **Copy** or **Download**.
4. If no download action appears on mobile, copy file contents and paste into a file in GitHub’s web editor.

If you still can’t access file actions on mobile, use **Option A (Codespaces)** below.

## What *is* possible

### Option A (easiest from phone): Use GitHub Codespaces
1. Open your repository on github.com.
2. Tap **Code**.
3. Open the **Codespaces** tab.
4. Tap **Create codespace on main** (or your branch).
5. In the Codespaces terminal, run:

```bash
git remote add origin https://github.com/<USERNAME>/<REPO>.git 2>/dev/null || git remote set-url origin https://github.com/<USERNAME>/<REPO>.git
git push -u origin "$(git branch --show-current)"
```

### Option B: Use a phone terminal app
- Android: Termux
- iOS/iPadOS: Blink Shell / a-Shell / iSH

Then run the same commands there.

## About "giving access"
- You can grant collaborator access in **Settings → Collaborators**, but that grants access to a GitHub account, not this local Codex runtime.
- For HTTPS pushes, GitHub may ask for a Personal Access Token (PAT) instead of your account password.
