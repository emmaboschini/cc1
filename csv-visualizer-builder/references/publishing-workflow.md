# GitHub Pages Publishing Workflow

To publish a separate CSV visualizer app within the same repository while maintaining a unique URL, follow this workflow.

## 1. Directory Structure
Instead of overwriting `index.html`, place each new app in its own subdirectory. This creates a separate URL at `username.github.io/repo/subdirectory/`.

```text
/workspaces/cc1/
├── index.html          (Main Landing Page)
└── apps/
    └── my-new-app/
        └── index.html  (The Visualizer App)
```

## 2. Preparation
- Copy the `visualizer.html` template from the skill assets to `apps/<app-name>/index.html`.
- Update the `<title>` and any specific text in the HTML to reflect the new dataset.

## 3. Git Workflow
Always use the `main` branch for publishing.

```bash
git add apps/<app-name>/index.html
git commit -m "Add new CSV visualizer for <dataset-name>"
git push origin main
```

## 4. GitHub Pages Configuration
- Ensure the repository is configured to deploy from the `main` branch at the root.
- The new app will be available at: `https://<username>.github.io/<repo>/apps/<app-name>/`

## 5. Verification
- Use `web_fetch` or a browser to verify the URL is live.
- Note: It may take 1-3 minutes for GitHub Pages to update after pushing.
