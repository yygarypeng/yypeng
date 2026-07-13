# Yuan-Yen Peng Portfolio Website

Static multi-page research portfolio for ATLAS PhD applications and evidence links. The site presents physics-informed reconstruction and inference for partially observed collider events, grounded in ATLAS HWW physics, analysis-level validation, Run 3 work, and HGTD detector-upgrade experience.

## Site Structure

- `index.html` — concise ATLAS physicist introduction and four quick profile cards
- `phd.html` — advisor-facing summary of the foundation offered and the project ownership sought
- `projects.html` — three flagship projects using `Physics question / My contribution / Evidence / Why it matters`
- `outputs.html` — public-safe evidence grouped into selected and technical output sections
- `contact.html` — sparse contact page with CERN email, internal-contact route, affiliation, CV/thesis/output links, and profiles
- `styles.css` — shared design tokens, typography, layout sections, responsive rules, focus states, and footer/logo treatment
- `assets/` — hero image, project figures, portrait, CV, and institutional logos

All pages share the same top navigation, KaTeX setup, Google Fonts setup, content-security policy, footer wording, and institutional logo footer.

Typography uses Google Fonts for cross-device consistency: `Marcellus` for display/title text, with Optima-style fallbacks, and `Inter` for body/UI text, with Helvetica Neue-style fallbacks. The CSS does not depend on local font files.

## Local Preview

No build step or package installation is required.

Choose either option:

1. Open `index.html` directly in a browser, or
2. Run a simple local static server from the repository root:

   ```bash
   python3 -m http.server 8000
   ```

   Then visit `http://localhost:8000/`.

## Customize Content

Update page content directly in the HTML files above, including:

- research positioning and project descriptions
- outputs, thesis/talk links, honors, and technical profiles
- contact links and preferred correspondence details
- footer `Last updated` text and institutional logo list

Keep pages compact. The intended text density is:

- Home: two short identity/fit paragraphs plus four cards
- PhD: one short opening, three evidence items, and one project-direction paragraph
- Projects: three flagship projects plus a compact additional-work note
- Outputs: two compact evidence sections
- Contact: minimal contact and profile links

If you add new media, place files in `assets/` and reference them with relative paths (for example `./assets/your-image.png`). Remove unused media before publishing.

When adding images, include meaningful `alt` text plus `width` and `height` attributes to avoid layout shift. Use `loading="lazy"` for below-fold images.

Every page includes KaTeX from jsDelivr and a `renderMathInElement(...)` block for inline physics notation. Preserve this block if editing page headers.

Every page also loads Google Fonts from `fonts.googleapis.com` / `fonts.gstatic.com`. If changing fonts, update both the `<link>` tags and the per-page content-security policy.

Do not publish local artifacts such as `.DS_Store`, `__MACOSX/`, local font folders, or zip exports.

## Continuous Integration

Every push to this repository (including commits from the GitHub Copilot coding agent) automatically runs the **Security & Visibility Check** workflow (`.github/workflows/security-check.yml`), which:

- **Secret scan** — runs [Gitleaks](https://github.com/gitleaks/gitleaks) to detect accidentally committed secrets or credentials.
- **Visibility check** — verifies that the repository remains public.

No manual steps are required; the checks run on every `push` event.

There is no lint, typecheck, unit-test, or build pipeline in this repository.

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
