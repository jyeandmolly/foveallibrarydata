<!-- *** AI-GENERATED — 28 October 2026 — Policy cl. 4.2 (code documentation) *** -->
# Foveal Bias Library

A reading-and-extraction workspace for the static foveal-bias literature: a summary table of studies whose values link to the exact spot in each PDF they came from, plus margin notes, stickies, pen, highlighter and `[[links]]` between papers.

The website holds no data. Everything is committed to a **separate private repository** through GitHub's API.

## Setup (about 10 minutes, once)

1. **Data repository (private).** On GitHub, create a new repository, e.g. `foveal-library-data`. Set it to **Private** and tick **Add a README file**.
2. **Access token.** Go to *Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token* (or https://github.com/settings/personal-access-tokens/new).
   - Repository access: **Only select repositories** → `foveal-library-data`
   - Permissions → Repository permissions → **Contents: Read and write**
   - Choose an expiry date. Copy the token.
3. **Website repository (public).** Create another repository, e.g. `foveal-library`. Upload everything in this folder: `index.html`, `README.md` and the `vendor` folder. Then *Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)` → Save*.
4. Open `https://<your-username>.github.io/foveal-library/` (it can take a minute to appear the first time). Enter your username, `foveal-library-data` and the token, then click **Connect**.

On another computer, open the same address and enter the details once in that browser.

**Why two repositories?** A GitHub Pages site is public. Keeping the site and the data apart means your notes and the PDFs (which can't be shared publicly) never sit in anything public. The page refuses to import PDFs if the data repository is public.

## Where things are stored (in the data repository)

| Path | Contents |
|---|---|
| `library/data.json` | Papers, experiment rows, notes, source pins and pen strokes |
| `library/pdfs/<id>.pdf` | One file per imported PDF |

## How saving works

- Changes are committed about 4 seconds after you stop typing (at most 20 seconds while you keep typing). **Ctrl/Cmd + S** saves immediately. The status at the top right says whether everything has reached GitHub.
- Every save is a commit, so the repository's history is a full undo record.
- If GitHub can't be reached, unsaved changes are kept in the browser and sent the next time you open the page.
- With the page open on two devices, each checks GitHub once a minute. If both change the library, the edits are merged: for any single note or table row, the most recent edit wins.

## Limits

- PDFs up to 50 MB each.
- You can't select or copy text inside the PDF viewer; type quotes into the source pin's note.
- Notes and pins are placed relative to the page of that PDF file. Replacing a PDF with a different edition will misplace them.

## Security

- The token is stored only in the browser you entered it in (local storage). Limit it to the data repository, give it an expiry date, and use **Settings → Forget token on this browser** on shared computers.
- The site loads no third-party code except fonts from Google Fonts. The PDF viewer is pdf.js 3.11.174 (Apache License 2.0), bundled in `vendor/pdfjs` with its licence.
