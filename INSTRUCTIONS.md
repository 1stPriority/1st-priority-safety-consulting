# Deploying this site to GitHub Pages (repository-ready)

## Option A — Using the GitHub web interface (quick)
1. Create a GitHub account at https://github.com (if you don't have one).
2. Click "New" to create a new repository.
   - Repository name: `1st-priority-safety-consulting` (or your choice)
   - Public: checked
   - Initialize: leave unchecked (we'll upload files)
3. After repository is created, click "Add file" → "Upload files".
4. Drag & drop the contents of this repository (all files and folders). Wait for upload.
5. Commit the upload (Commit changes).
6. Go to "Settings" → "Pages" (left menu) → Under "Build and deployment", select:
   - Source: Branch: `main` (or `gh-pages`), Folder: `/ (root)`
   - Click Save.
7. Your site will be published at `https://<your-username>.github.io/<repo-name>/` within a minute.

## Option B — Using git (recommended for future edits)
(Run these commands on your computer — replace placeholders)

```bash
# from the directory that contains this repo folder
cd path/to/website_repo
git init
git add .
git commit -m "Initial site commit"
# create repo on GitHub (you can use the web UI instead); then:
git remote add origin https://github.com/<your-username>/<repo-name>.git
git branch -M main
git push -u origin main
```

Then configure GitHub Pages in the repository Settings → Pages as in Option A.

## Using a custom domain
- Create a file named `CNAME` with your domain, e.g. `www.example.com`.
- Buy the domain from a registrar and set DNS:
  - For `www` use a CNAME to `<your-username>.github.io`
  - For apex domain (`example.com`) add A records to GitHub Pages IPs:
    - 185.199.108.153
    - 185.199.109.153
    - 185.199.110.153
    - 185.199.111.153
- In GitHub repository Settings → Pages, enter the custom domain and save.

## Notes
- For HTTPS, GitHub Pages provides HTTPS automatically for `github.io` domains and often for custom domains after DNS propagates.
- If you prefer the site to be at the root (username.github.io), name the repository `<your-username>.github.io`.
