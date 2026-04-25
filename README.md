# Yuan-Yen Peng Portfolio Website

Static multi-page research portfolio for physics PhD applications and ATLAS-facing review. The site presents one coherent arc: ATLAS Higgs measurements with missing neutrinos, ML-based event reconstruction, validation for collaboration workflows, and HGTD detector-software infrastructure.

## Site Structure

- `index.html` — research-focus homepage, committee snapshot, evidence links, and core program summary
- `research.html` — scientific arc from missing-neutrino reconstruction to reusable inference tools
- `projects.html` — project stories ordered from physics motivation to reconstruction, detector software, and Run 3 analysis support
- `outputs.html` — verifiable evidence: thesis, ATLAS note, presentations, honors, and technical footprint
- `contact.html` — CERN email, research profiles, and availability
- `styles.css` — shared design tokens, typography, layout sections, responsive rules, focus states, and footer/logo treatment
- `assets/` — hero image, project figures, portrait, CV, and institutional logos

All pages share the same top navigation, KaTeX setup, footer wording, and institutional logo footer.

The stylesheet is organized by purpose: base rules, header/hero, intro, content, project rows, lists/footer, and responsive overrides. Typography uses an Optima-led display stack for headings/kickers and a serif stack for long-form academic body copy.

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

If you add new media, place files in `assets/` and reference them with relative paths (for example `./assets/your-image.png`).

When adding images, include meaningful `alt` text plus `width` and `height` attributes to avoid layout shift. Use `loading="lazy"` for below-fold images.

Every page includes KaTeX from jsDelivr and a `renderMathInElement(...)` block for inline physics notation. Preserve this block if editing page headers.

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
