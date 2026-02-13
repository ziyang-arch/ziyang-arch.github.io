# Deployment Guide

## Quick Deployment Steps

### Step 1: Add Remote Repository

If you haven't created the GitHub repository yet:
1. Go to https://github.com/new
2. Repository name: `ziyang-arch.github.io` (must match your GitHub username)
3. Make it **Public** (required for free GitHub Pages)
4. **Do NOT** initialize with README, .gitignore, or license
5. Click "Create repository"

Then add the remote (SSH recommended):

```bash
cd my-gate
git remote add origin git@github.com:ziyang-arch/ziyang-arch.github.io.git
```

If you see a `Permission denied (publickey)` error when pushing, you need to set up an SSH key (see **SSH Setup** section below).

### Step 2: Push to GitHub

```bash
git push -u origin master
```

This will:
- Upload all your files to GitHub
- Set `master` as the upstream branch
- Trigger the GitHub Actions workflow

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub: `https://github.com/ziyang-arch/ziyang-arch.github.io`
2. Click **Settings** (top navigation bar)
3. Click **Pages** (left sidebar)
4. Under **Build and deployment**:
   - **Source**: Select **"GitHub Actions"** (NOT "Deploy from a branch")
5. Save the settings

### Step 4: Monitor Deployment

1. Click the **Actions** tab in your repository
2. You should see "Deploy Hugo site to Pages" workflow running
3. Wait for it to complete (usually 1-2 minutes)
4. When it shows a green checkmark ✅, your site is deployed!

### Step 5: Access Your Website

Your site will be live at:
**https://ziyang-arch.github.io**

(It may take a few minutes after the workflow completes for DNS to propagate)

---

## Troubleshooting

### If GitHub Actions Fails

1. Click on the failed workflow run
2. Check the error messages
3. Common issues:
   - **Theme not found**: Make sure `themes/PaperMod` is properly set up as a submodule
   - **Build errors**: Check your `hugo.toml` for syntax errors
   - **Missing files**: Ensure all content files are committed

### If Pages Source Shows "None"

- Make sure you selected **"GitHub Actions"** as the source, not a branch
- The workflow must run successfully at least once

### If Site Shows 404

- Wait 5-10 minutes for DNS propagation
- Check that `baseURL` in `hugo.toml` matches your GitHub Pages URL
- Verify the workflow completed successfully

---

## Future Updates

After initial deployment, updating your site is simple:

```bash
# 1. Make your changes (edit markdown files, etc.)
# 2. Stage changes
git add .

# 3. Commit
git commit -m "Added new blog post: [title]"

# 4. Push (triggers automatic rebuild and deployment)
git push origin master
```

The site will automatically rebuild and deploy in ~1-2 minutes!

---

## Verify Local Build First

Before pushing, test locally:

```bash
cd my-gate
hugo server -D
```

Visit `http://localhost:1313` to preview your site. Fix any issues before pushing.

---

## SSH Setup (for git@github.com URLs)

If `git push` fails with `Permission denied (publickey)`:

1. **Generate an SSH key (if you don't have one)**:
   ```bash
   ssh-keygen -t ed25519 -C "your_email@example.com"
   # When prompted for a file path, you can press Enter to accept default (~/.ssh/id_ed25519)
   # You can optionally set a passphrase
   ```
2. **Start the SSH agent and add your key**:
   ```bash
   eval \"$(ssh-agent -s)\"
   ssh-add ~/.ssh/id_ed25519
   ```
3. **Copy your public key**:
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```
4. **Add it to GitHub**:
   - Go to GitHub → Settings → **SSH and GPG keys**
   - Click **New SSH key**
   - Paste the contents of `id_ed25519.pub`
5. **Test the connection**:
   ```bash
   ssh -T git@github.com
   ```
   If it says something like *“Hi ziyang-arch! You've successfully authenticated…”*, you're good.

Then you can:
```bash
cd my-gate
git push -u origin master
```

