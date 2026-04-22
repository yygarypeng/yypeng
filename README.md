# Yuan-Yen Peng Portfolio Website

This repository hosts a static multi-page personal portfolio website focused on ATLAS experimental physics, machine-learning reconstruction, and HGTD software work.

## Site Structure

- `index.html` — home and professional summary
- `research.html` — research themes and technical stack
- `projects.html` — flagship project highlights
- `outputs.html` — thesis, talks, and honors
- `contact.html` — contact channels and profile links
- `styles.css` — shared site styling
- `assets/` — images used across pages

## Local Preview

No build step is required.

Choose either option:

1. Open `index.html` directly in a browser, or
2. Run a simple local static server from the repository root:

   ```bash
   python3 -m http.server 8000
   ```

   Then visit `http://localhost:8000/`.

## Customize Content

Update page content directly in the HTML files above, including:

- research and project descriptions
- outputs (thesis/talk links and achievements)
- contact links and profile information
- footer "Last updated" timestamps

If you add new media, place files in `assets/` and reference them with relative paths (for example `./assets/your-image.png`).

## Deploy with GitHub Pages

This repository is a plain static site and can be deployed from the root folder.

1. Push to GitHub.
2. Open **Settings → Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**.
4. Choose your branch and `/` (root) folder.
5. Save.

URL format:

- `https://<username>.github.io/` for a user site repo (`<username>.github.io`)
- `https://<username>.github.io/<repo>/` for a project site repo
