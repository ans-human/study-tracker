# Study Tracker — GitHub Pages setup

## 1. Create the repo
1. On GitHub, create a new repository (public or private both work) — e.g. `study-tracker`.
2. Upload `index.html` to the root of the repo (or drag-and-drop it in the GitHub web UI).

## 2. Turn on GitHub Pages
1. In the repo: **Settings → Pages**.
2. Under "Build and deployment", set **Source** to `Deploy from a branch`.
3. Pick your branch (usually `main`) and folder `/ (root)`, then **Save**.
4. GitHub gives you a URL like `https://<your-username>.github.io/study-tracker/` — that's your tracker, from any device.

## 3. Create a personal access token (so the page can save your progress)
1. GitHub → your profile photo → **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. **Repository access**: select "Only select repositories" → choose this one repo.
3. **Permissions**: under Repository permissions, set **Contents** to **Read and write**. Leave everything else as "No access".
4. Generate the token and copy it — GitHub only shows it once.

## 4. Connect the page
1. Open your GitHub Pages URL.
2. Click the gear icon.
3. Fill in:
   - **GitHub username / org**: your username
   - **Repository name**: `study-tracker` (or whatever you named it)
   - **Branch**: `main`
   - **File path**: `progress.json` (this file will be created automatically on first save)
   - **Personal access token**: the token from step 3
4. Save & sync.

Do this once per device/browser you use — the token is stored only in that browser's local storage, never in the repo itself. Your actual progress lives in `progress.json` in the repo, so every device that's connected reads and writes the same file.

## Notes
- Checking an item saves automatically about a second after you stop clicking.
- If you edit on two devices within the same second or two, the last save wins — not a real concern for a personal tracker used one device at a time.
- If you ever want to revoke access, delete the token from GitHub's token settings page — the page will just start failing to sync until you add a new one.
