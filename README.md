<!-- *** AI-GENERATED — 28 October 2026 — Policy cl. 4.2 (code documentation) *** -->
# Foveal Bias Library

A reading-and-extraction workspace for the static foveal-bias literature: a summary table of studies whose values link to the exact spot in each PDF they came from, plus margin notes, stickies, pen, highlighter and `[[links]]` between papers.

The website holds no data. Everything is committed to a **separate private repository** through GitHub's API.

## Updating the website (when you get a new version)

1. Unzip `foveal-library.zip`. Open the `foveal-library` folder inside it.
2. On GitHub, open your **website** repository (e.g. `foveal-library`, not the data one) → **Add file → Upload files**.
3. Drag in everything from the folder: `index.html`, `README.md`, and the `brand` and `vendor` folders. Files with the same name are replaced.
4. Click **Commit changes**. Wait about a minute, then reload the site with **Cmd/Ctrl + Shift + R**.

Nothing needs to change in the data repository. Your library, notes and PDFs are untouched.

## Setup (about 10 minutes, once)

1. **Data repository (private).** On GitHub, create a new repository, e.g. `foveal-library-data`. Set it to **Private** and tick **Add a README file**.
2. **Access token.** Go to *Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token* (or https://github.com/settings/personal-access-tokens/new).
   - Repository access: **Only select repositories** → `foveal-library-data`
   - Permissions → Repository permissions → **Contents: Read and write**
   - Choose an expiry date. Copy the token.
3. **Website repository (public).** Create another repository, e.g. `foveal-library`. Upload everything in this folder: `index.html`, `README.md`, and the `vendor` and `brand` folders. Then *Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)` → Save*.
4. Open `https://<your-username>.github.io/foveal-library/` (it can take a minute to appear the first time). Enter your username, `foveal-library-data` and the token, then click **Connect**.

On another computer, open the same address and enter the details once in that browser.

**Why two repositories?** A GitHub Pages site is public. Keeping the site and the data apart means your notes and the PDFs (which can't be shared publicly) never sit in anything public. The page refuses to import PDFs if the data repository is public.

## Where things are stored (in the data repository)

| Path | Contents |
|---|---|
| `library/data.json` | Papers, experiment rows, notes, source pins and pen strokes |
| `library/pdfs/<id>.pdf` | One file per imported PDF |
| `library/text/<id>.json` | The text of each PDF, used by search (created automatically) |

## How saving works

- Changes are committed about 4 seconds after you stop typing (at most 20 seconds while you keep typing). **Ctrl/Cmd + S** saves immediately. The status at the top right says whether everything has reached GitHub.
- Every save is a commit, so the repository's history is a full undo record.
- If GitHub can't be reached, unsaved changes are kept in the browser and sent the next time you open the page.
- With the page open on two devices, each checks GitHub once a minute. If both change the library, the edits are merged: for any single note or table row, the most recent edit wins.

## Search

- Type in the search box above the table. It looks through the text of every PDF, plus each paper's label, reference, reading notes and annotations. Results list each matching paper with its abstract (when the PDF has a heading called "Abstract"), the matching passages with page numbers, and any of your notes that match.
- Click a passage to open the paper at that page with the word outlined. The chip at the top ("Highlighting …") turns the outlines off.
- Every word must appear in a paper for it to be listed. Put words in quotes to search for a phrase: `"eye tracking"`. Parts of words match too: `fovea` finds `foveal`.
- **First time:** the site reads the text of each PDF once and saves it to `library/text/` in the data repository. With many papers this takes a minute or two. You'll see "Reading the text of your PDFs: 3 of 40" and a commit per paper. New imports are read straight away.
- Scanned PDFs without a text layer can't be searched (only their notes can).

## Export with notes

**Export PDF** (top of each paper) downloads the paper with your annotations: the original pages, untouched and still searchable, with your pen, highlights, stickers, stickies and source pins drawn on. A column on the right lists every margin note, sticky, source pin and sticker note beside the spot it belongs to. A last page has your reading notes and the paper's rows from the summary table.

Notes are set in Helvetica, which lacks some characters: Greek letters and maths signs are spelled out (α → alpha, ≈ → ~), and anything else becomes "?".

## Look

- **Header band.** It's a collage of square eye photographs, sharp at the pointer and blurred with distance from it. When the pointer is still, it makes slow "saccades" on its own; with *Reduce motion* turned on in your system settings, it stays put.
- **Photos.** There are 26, all from Unsplash, used under the Unsplash License: free to use, no permission or credit needed. The one restriction is that you can't compile Unsplash images into a competing image service. They are loaded from Unsplash's image server, which crops each one to a square. The list, with each photo's Unsplash page, is at the top of the script in `index.html` (search for `EYES`). To swap a photo, replace its id. If the photos can't load (offline, or blocked by a network), the band falls back to a field of coloured squares.
- **Logo.** Jye's eye mark with a wireframe globe for a pupil. In the header it opens when the page loads, the globe turns, and it blinks every few seconds (still if *Reduce motion* is on). It's black on the light theme and the original green (`#41ff78`) on the dark theme. To change that, edit `--logo` near the top of the styles in `index.html`. The `brand` folder holds still versions: `eye.svg` (black), `eye-dark.svg` (off-white), `eye-green.svg` (green), and `eye-small.svg` and `eye-small-green.svg` with thicker lines for anything under about 40 px wide.

## Limits

- PDFs up to 50 MB each.
- You can't select or copy text inside the PDF viewer; type quotes into the source pin's note. (Search still finds the words.)
- Notes and pins are placed relative to the page of that PDF file. Replacing a PDF with a different edition will misplace them.

## Security

- The token is stored only in the browser you entered it in (local storage). Limit it to the data repository, give it an expiry date, and use **Settings → Forget token on this browser** on shared computers.
- The site loads no third-party code. It does load fonts from Google Fonts and the eye photos from Unsplash, so those two services see each visitor's IP address. The PDF viewer is pdf.js 3.11.174 (Apache License 2.0), bundled in `vendor/pdfjs` with its licence. Export uses pdf-lib 1.17.1 (MIT License), bundled in `vendor/pdf-lib` with its licence and loaded only when you export.
