<!-- *** AI-GENERATED — 28 October 2026 — Policy cl. 4.2 (code documentation) *** -->
<!-- *** AI-GENERATED — 29 October 2026 — Policy cl. 4.2 (code documentation) — pages, to-dos, text selection *** -->
<!-- *** AI-GENERATED — 30 October 2026 — Policy cl. 4.2 (code documentation) — to-do list, Notes, deleting papers *** -->
<!-- *** AI-GENERATED — 30 October 2026 — Policy cl. 4.2 (code documentation) — journal pages, page tools and paper pins in Notes *** -->
<!-- *** AI-GENERATED — 30 October 2026 — Policy cl. 4.2 (code documentation) — editable header, Export PDF, white pages *** -->
<!-- *** AI-GENERATED — 30 October 2026 — Policy cl. 4.2 (code documentation) — header band without blur *** -->
<!-- *** AI-GENERATED — 30 October 2026 — Policy cl. 4.2 (code documentation) — link pins between papers *** -->
<!-- *** AI-GENERATED — 30 October 2026 — Policy cl. 4.2 (code documentation) — sync message *** -->
<!-- *** AI-GENERATED — 3 November 2026 — Policy cl. 4.2 (code documentation) — note editor rewritten (Osaka 1977 style, breaks, own editing) *** -->
<!-- *** AI-GENERATED — 3 November 2026 — Policy cl. 4.2 (code documentation) — figure sizes, contents, links on words, margin notes on words, back-link eye *** -->
<!-- *** AI-GENERATED — 3 November 2026 — Policy cl. 4.2 (code documentation) — paper review headings *** -->
<!-- *** AI-GENERATED — 3 November 2026 — Policy cl. 4.2 (code documentation) — online sources, opening in a new tab, alternating running heads *** -->
<!-- *** AI-GENERATED — 4 November 2026 — Policy cl. 4.2 (code documentation) — Themes (thematic analysis) *** -->
<!-- *** AI-GENERATED — 5 November 2026 — Policy cl. 4.2 (code documentation); Policy cl. 3.3 overridden under cl. 10 for the citation feature only — citations and reference lists; paper review headings under Headings; quieter main pages *** -->
<!-- *** AI-GENERATED — 5 November 2026 — Policy cl. 4.2 (code documentation) — paragraph labels (¶); Export PDF ▸ APA 7 professional paper; Reference details card when PDFs are added *** -->
<!-- *** AI-GENERATED — 5 November 2026 — Policy cl. 4.2 (code documentation); Policy cl. 3.3 overridden under cl. 10 for this request only — Build from parts *** -->
<!-- *** AI-GENERATED — 5 November 2026 — Policy cl. 4.2 (code documentation) — Reference button on the PDF; references with no PDF *** -->
<!-- *** AI-GENERATED — 5 November 2026 — Policy cl. 4.2 (code documentation) — section (§) and paragraph (¶) labels in grey, set like normal text *** -->
<!-- *** AI-GENERATED — 5 November 2026 — Policy cl. 4.2 (code documentation) — APA paper laid out page by page; reference list in a note set like its text *** -->
<!-- *** AI-GENERATED — 9 November 2026 — Policy cl. 4.2 (code documentation) — sidebar in place of the eye-photo header; all animation removed; quieter headings *** -->
<!-- *** AI-GENERATED — 9 November 2026 — Policy cl. 4.2 (code documentation) — Home cards with the eye photos (option C) *** -->
<!-- *** AI-GENERATED — 10 November 2026 — Policy cl. 4.2 (code documentation) — Export PDF: no line is ever cut off or lost *** -->
<!-- *** AI-GENERATED — 10 November 2026 — Policy cl. 4.2 (code documentation) — Export PDF ▸ As it looks, second version: each page holds its own text; sidebar line under the name *** -->
<!-- *** AI-GENERATED — 10 November 2026 — Policy cl. 4.2 (code documentation) — renamed Perception Research Library; APA: authors and affiliations, ORCID iDs, line numbers, word count, lines fixed before printing *** -->
# Perception Research Library

A reading-and-extraction workspace for a research literature: a summary table of studies whose values link to the exact spot in each PDF they came from, plus margin notes, stickies, pen, highlighter and `[[links]]` between papers.

The website holds no data. Everything is committed to a **separate private repository** through GitHub's API.

## Updating the website (when you get a new version)

1. Unzip `foveal-library.zip`. Open the `foveal-library` folder inside it.
2. On GitHub, open your **website** repository (e.g. `foveal-library`, not the data one) → **Add file → Upload files**.
3. Drag in everything from the folder: `index.html`, `README.md`, and the `brand` and `vendor` folders. Files with the same name are replaced.
4. Click **Commit changes**. Wait about a minute, then reload the site with **Cmd/Ctrl + Shift + R**.

Nothing needs to change in the data repository. Your library, notes and PDFs are untouched.

**After this update, reload every copy of the site you have open** (other tabs, other computers). A copy from before Themes existed doesn't know about them, and if it saves it leaves your themes out of `data.json`.

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
| `library/data.json` | Papers, experiment rows, annotations, source pins, pen strokes, tags, columns, your to-dos, your Notes, and your themes and coded passages |
| `library/pdfs/<id>.pdf` | One file per imported PDF |
| `library/text/<id>.json` | The text of each PDF, used by search (created automatically) |
| `library/images/<note>-<id>.<ext>` | Images in your Notes |

## How saving works

- Changes are committed about 4 seconds after you stop typing (at most 20 seconds while you keep typing). **Ctrl/Cmd + S** saves immediately. The status at the top right says whether everything has reached GitHub.
- Every save is a commit, so the repository's history is a full undo record.
- If GitHub can't be reached, unsaved changes are kept in the browser and sent the next time you open the page.
- With the page open on two devices, each checks GitHub once a minute. If both change the library, the edits are merged: for any single note or table row, the most recent edit wins.
- "Updated with changes saved from another tab or device" means the library on GitHub changed somewhere other than this tab: usually a second tab or window with the site open, or your phone or another computer. Only someone with your token (or access to the private data repository) can save to it; to be sure, revoke the token on GitHub and make a new one.

## Sidebar, Home and tag pages

- On the library pages a **sidebar** runs down the left: the eye logo and the library's name, then **Home**, **All literature**, **Notes** and **Themes**, then each of your **Tags**, each with its count. The page you're on is shaded. **Settings** and the save state ("Saved to GitHub …") sit at the foot. Papers and notes open full width, without the sidebar, with a back link at the top left.
- Each entry is an ordinary link, so Ctrl/Cmd+click opens it in a new tab.
- **Home** has a line of counts, the Import / Add paper / Export CSV buttons, then **Collections**: a card for All literature, Notes, Themes and each tag, each with an animal-eye photo, its name and its count. Click a card to open it. Your to-do list is below.
- Click a tag (or **All literature**, which holds every paper) to open its page: the tag's counts at the top, then its papers as a list. **Summary table** swaps the list for the table; **Papers** swaps back. Search and Sort are here and work within the tag.
- Each tag page has its own address, e.g. `…/#methods` or `…/#all-literature`, so the browser's Back button and bookmarks work. A paper's back link returns to the tag you came from.
- On a narrow window (under 900 px, e.g. a phone) the sidebar becomes a band across the top; swipe a row sideways to see more tags.
- Importing several PDFs at once opens All literature so you can see them.

## Tags

- Open a paper and click **Add tags** in the bar at the top. Tick the tags that apply, or type a new one and press Enter. The ✎ renames a tag everywhere, and × deletes it from every paper.
- Tags are listed in the sidebar, under Home, All literature, Notes and Themes. With many tags the list scrolls inside the sidebar.
- Drag a tag up or down the sidebar list to change the order. On a touch screen, hold it a moment first. (Not on a narrow window, where the sidebar is a band.) A click within half a second after a drag is ignored.
- **Export CSV** has a Tags column.

## Notes

- **Notes** in the sidebar opens your notes: a list, newest edit first, with search and **New note**. Each note opens as its own page.
- **Look.** A note is set like *The Journal of Psychology* in the 1970s (Osaka, 1977, was the model) on plain white pages: Times-style type (STIX Two Text), justified text with indented paragraphs and automatic hyphenation, and on page 1 a small header line, the title in spaced capitals, a line in italics (the date it was last edited) and a short rule. Pages after the first have a running head in small capitals with the page number outside: the author on left-hand pages, the title on right-hand pages.
- **Header line and running heads.** Click the small line above the title to change it (empty it for none). The running heads alternate, as in a journal: left-hand (even) pages carry the author, starting as your name, and right-hand (odd) pages carry the note's title. Click either at the top of a page to change it on every page of that side.
- **Styles** (the first button in the toolbar, which also shows the style the cursor is in): **Normal text** (11.5 pt); **Heading**, centred in small capitals, as in "A. Introduction"; **Subheading**, in italics; **§ Section label** and **¶ Paragraph label**: planning lines saying what the section or paragraph below is about. They're set exactly like normal text (same font, size, alignment and indent), only in grey, with § or ¶ in the margin. **Quotation**, in smaller italic type and indented. Enter after a heading, subheading or label goes back to Normal text. Shortcuts: Ctrl/Cmd+Alt+0 Normal text, +1 Heading, +2 Subheading, +3 Paragraph label, +4 Section label. In the outline, section labels sit at the second level and paragraph labels at the third. Labels aren't counted in the word count, are left out of the contents and of the APA export, and print in grey in the *As it looks* export.
- **Toolbar:** style, bold, italic, bulleted and numbered lists, **Link**, **Insert**, undo/redo. Shortcuts: Ctrl/Cmd+B, I, K; Ctrl/Cmd+Shift+8 bullets, +7 numbers; Ctrl/Cmd+Z and Ctrl/Cmd+Shift+Z.
- **Insert:** **Figure (image)**, **Paper pin**, **Paper review heading**, **Table of contents**, **Citation**, **Reference list**, **Line break** (Shift+Enter: a new line in the same paragraph, not indented), **Section break** (a short centred rule; the text carries on below it) and **Page break** (Ctrl/Cmd+Enter: what follows starts the next page).
- **Editing.** Enter at the start of a line adds an empty line above it. Enter on an empty list item ends the list, and Enter on an empty quotation line goes back to Normal text. Backspace at the start of a list item removes its bullet; Backspace just after a rule or page break removes it. Backspace and Delete next to a figure move into its caption instead of deleting it. When two paragraphs are joined, the first one's style is kept, and nothing of the other's styling is carried along.
- **Pages.** Nothing ever shows outside a page, even while you type: the page breaks are recalculated with every keystroke. A paragraph breaks between lines, never leaving a single line of it alone at the foot of a page or the head of the next, and a hyphenated word never breaks across two pages. Headings, section rules and figures move to the next page whole, and a heading stays with the paragraph after it. The arrow keys move from one page to the next line by line.
- **Figures.** Insert ▸ **Figure (image)** (or paste or drop an image) adds the picture, centred, then "Figure 1" in small capitals, a title line and a caption to fill in; Enter moves from the title to the caption and back to the text. Figures renumber themselves. Hover over a figure for **Small**, **Medium**, **Large** and **Full** (a third, half, three quarters or all of the text width; a small picture is never enlarged). A figure is never taller than a page. Hover one and click × twice to remove it. Images are committed to `library/images/` (private data repository only); photos wider than 2400 px are scaled down.
- **Paper review headings** (formerly *review section headings*). Style menu ▸ **Paper review heading…**, or Insert ▸ **Paper review heading**, then find a paper in your library. A heading goes in where the cursor is, and the cursor moves to a fresh line below it, ready for you to write about the paper. The heading is one heading set on two centred lines in small capitals: the paper's label (bold and underlined), and under it the paper's title, both exactly as you typed them. Nothing is put together, shortened or reordered for you. The first time you use a paper, a small box asks for its title (and lets you adjust the label); both are saved on the paper, so its paper review heading reads the same in every note. You can also type or change the title in the paper's **Notes & sources** tab (**Title**), and the headings follow. For a source you don't keep in your library (a website, or a PDF too big to keep), choose **Online source (not in your library)** in the same box and type the two lines and, if it has one, its web address; those belong to that heading only. Click a heading (or right-click it) to open the paper or source here or in a new tab, copy its address, change it or remove it; Ctrl/Cmd+click or the middle mouse button opens it in a new tab. It ranks one level below a Heading: set a little smaller than Headings, and indented one level in the outline and the contents. In the outline it is listed once, under its first line; in the contents its first line is in small capitals (not bold or underlined) with the title beneath. It can't be typed into directly, and highlights, links and margin notes can't be put on it.
- **Table of contents.** Insert ▸ **Table of contents** puts a list of the headings and subheadings, with their page numbers, where the cursor is. It keeps itself up to date as you write, headings in small capitals and subheadings in italics, with dotted leaders to the numbers. Click an entry to go to it. Hover over it and click × twice to remove it.
- **Links on words.** Select words, then **Link** (or Ctrl/Cmd+K). Paste a web address and press Enter, or type to find a paper: **Pick the spot →** takes you to its PDF to click the place you mean, and **No spot** links the paper itself. The words look exactly as before, with no colour or underline. With the cursor in linked words, a bubble shows where they go, with **Open**, **New tab**, **Change** and **Remove**. Ctrl/Cmd+click or the middle mouse button opens a link in a new tab (a paper link opens its PDF at the spot). Right-click gives **Open in new tab**, **Open**, **Copy link address**, **Change link** and **Remove link**.
- **Paper pin.** Put the cursor where you want the pin, choose Insert ▸ **Paper pin**, find the paper, then click the spot in its PDF that you mean (Esc cancels). A small pin goes into the text (hover over it to see the paper and page). Click it to open the paper at that spot, marked for a few seconds; Ctrl/Cmd+click or the middle button opens it in a new tab, and right-click offers both and Copy link address. **No spot** links the paper without a spot (papers without a PDF are always linked that way). A deleted paper's pin is greyed out.
- **Page tools** (second toolbar row), as on a PDF: **Write** (V), Margin note (M), Sticky (S), Sticker (K, including TODO checklists, which also appear in the front-page To do list), Pen (P), Highlight (H), Erase (X). Highlighting words marks them in the text, so the highlight moves with the words; Erase removes it. With **Margin note**, select the words the note is about: they are highlighted in the note's colour, and the note sits beside them in the margin and moves with them, onto another page if they move there. Changing the note's colour changes its words' too, and deleting the note removes the highlight. Erase on the words removes both, but only while the note is empty. Margin notes made before this stay where they were. Stickers, stickies and pen strokes stay where you put them on the page. The letter keys switch tools only when you are not typing in the note.
- **Find in this note** (the box in the toolbar, or Ctrl/Cmd+F): outlines every match and counts them; Enter / Shift+Enter step through them, Esc clears.
- **Search.** The Notes page searches only your notes. The search on **All literature** lists matching notes above the papers; opening one shows the matches.
- **Pasting.** Pasted text keeps headings, bold, italic (Google Docs and Word included), lists and links, and takes on the note's typesetting; fonts, sizes, colours and tables are dropped. Plain text keeps its paragraphs; lines of one paragraph copied out of a PDF are joined back together.
- **Export PDF ▸ APA 7 professional paper…** A box asks for what only you can supply: title; the authors, one row each (name, the numbers of their affiliations, ORCID iD if they have one; **Add author**, ↑ to move one up); the affiliations, one per line (line 1 is affiliation 1); running head (50 characters or fewer, printed in capitals); your author note paragraphs; abstract; keywords; **Line numbers** (on unless you untick it); **Word count on the title page** (off unless you tick it); and paper size (A4 or US Letter). It starts filled with the note's title, your name and the title in capitals as the running head, and it remembers what you type for this note. It warns you if the note cites works but has no reference list, or if a citation or reference is missing something. Then the print window opens with:
  - the running head top left and page numbers top right on every page;
  - a title page (APA 7, sections 2.3–2.7): the title, then the authors ("A and B"; "A, B, and C"). When two or more authors don't all share the same affiliations, each name carries superscript numbers and each affiliation line starts with its number; otherwise there are no numbers. With **Word count** ticked, the count follows the affiliations: the words of the text from its first heading up to the reference list, without the title, figures and references. At the foot, **Author Note**: one line per ORCID iD ("Name https://orcid.org/…"), then your paragraphs exactly as you wrote them (APA's order: changes of affiliation, disclosures and acknowledgments, correspondence). The site doesn't word any of it for you;
  - **line numbers** in the left margin, one count running on from the first line of the title page to the last reference (the running head and page numbers aren't counted). Every line of the paper is fixed as laid out before the print window opens, as Word does, so the browser can't re-wrap the text while printing and each number stays beside its line;
  - an abstract page (if you wrote an abstract);
  - the text under its title, in Times New Roman 12 pt, double spaced, left aligned, with 0.5-inch paragraph indents;
  - Heading as Level 1 (bold, centred), paper review heading as Level 2 (bold, flush left, both lines), Subheading as Level 3 (bold italic);
  - quotations as indented block quotations;
  - figures as "Figure N", then the title in italics, the image and your caption;
  - the reference list from a new page.

  Left out: section and paragraph labels, the contents, section-break rules, pins, highlights, margin notes, stickies, stickers and pen. Your words aren't changed: headings keep the capitals you typed (APA uses title case), and "Note." isn't added before figure captions. The pages are laid out by the site itself: each page carries its own 1-inch margins, running head and page number. That means the paper comes out right whatever the print window's margin setting (use *None* or *Default*; turn off *Headers and footers*).

- **Splitting text across pages:** a paragraph, quotation, list item or reference that doesn't fit is split between lines, keeping at least two lines on each page. A word hyphenated at the foot of a page goes over to the next page whole.
- **No line is ever cut off:** once the pictures have loaded, every page is checked, and any line that would reach past the bottom margin moves to the next page. If something still did (it shouldn't), it would print into the margin rather than vanish.
- **Keeping things whole:** headings and figures move to the next page whole, and a heading moves with what follows it. A figure taller than a page is shrunk to fit.
- **Empty lines** in the note are dropped (APA has no blank lines).
- **Block quotations** are all set upright, as APA requires, so any italics typed or pasted inside a quotation are removed in the paper only. The note keeps them.
- **Export PDF ▸ As it looks** opens the print window with the note laid out exactly as on screen, page for page, with its highlights, stickers, stickies and pen; a last page lists the margin notes, stickies and to-do lists. Choose **Save as PDF** as the printer.
  - **No line is ever cut off or lost.** Each printed page holds only its own text: the note is split where the screen breaks its pages, and a paragraph that runs over is split between the same two lines. Nothing on a printed page is clipped, so no line can fall between two pages or be sliced by a page edge, even if the browser sets the text a little differently when it prints.
  - If the print copy comes out longer than on screen, the lines that don't fit move to the top of the next page. If the browser still sets a page a line longer while printing, that line runs into the bottom margin rather than being lost.
  - A margin note or sticky longer than a page continues on the next page of the list.
  - Only something taller than a whole page (a very tall figure) can still run off the foot of the page. A message says which page when that happens. In Chrome or Edge the PDF pages are the same size as the note's pages; other browsers may add margins (turn off "Headers and footers").
- Notes save a moment after you stop typing. **Delete note** (top right of a note, or in the list) asks once more, then removes the note, its annotations and its images.

## Citations and reference lists (in notes)

*The ordering and lettering rules below were written by AI under a one-off override of your Policy cl. 3.3 (5 November 2026). Check them against the APA Publication Manual (7th ed.) before relying on them.*

**On each paper** (**Notes & sources** tab) you type three things yourself:

- **APA reference:** the whole entry as it should stand in a reference list. Put \*asterisks\* around words in italics.
- **In-text, in brackets:** the authors, a comma and the year, as they go inside brackets for this work alone.
- **In-text, in a sentence:** the authors, then the year in brackets.

A line under the fields tells you if one can't be read, if the years differ, or if you've typed an a or b after a year (leave those out; see below).

**Build from parts** *(written by AI under a second one-off override of Policy cl. 3.3, 5 November 2026; check it against the APA manual before relying on it)*. Under the three fields, and in the Reference details card, **Build from parts…** opens a form:

- **Source type:** journal article, book, chapter in an edited book, or webpage.
- **Parts:** authors (one per line as *Surname, initials*, or a group's name), year or date, title, journal or publisher or website, volume, issue, pages, editors, edition, DOI or URL.
- **Preview:** shows the assembled APA reference and both in-text forms as you type, says what's still needed, and lists any optional parts left out.
- **Fill the three fields** puts them into the paper's fields, where you can still change them. If those fields already hold something different, it asks first. The parts are kept on the paper.

What it does with your parts (APA 7):

- **Authors (§9.8–9.10):** initials set as *A. B.* (a given name typed in full becomes its initial). "&" goes before the last of 2–20 authors; 21 or more become the first 19, ". . .", then the last.
- **Reference patterns:** journal article (§10.1), book or edited book with (Ed.)/(Eds.) (§10.2), chapter "In … (Eds.), *Book* (ed., pp.)" (§10.3), and webpage (§10.16, with the site name dropped when it matches a group author).
- **Small fixes:** en dashes in page ranges, DOIs as https://doi.org/ links, editions such as *2nd ed.*
- **In-text (§8.17):** one surname; two joined by "&" in brackets and "and" in a sentence; three or more as the first surname with "et al."; the year only.

Your words are otherwise left alone. Titles keep the capitals you typed (APA wants sentence case for titles and title case for journal names). Nothing comes from the PDF, and nothing missing is supplied: a missing required part means nothing is filled. Not covered: reports, theses, conference papers, datasets and other source types (type those references in the field), and webpages with no author.

**On the PDF itself:** **Reference** (beside the find box, above the pages) opens the same card for the paper you're reading. A small dot on it means the paper has no APA reference yet.

**A reference with no PDF** (a book you don't have here, say): in a note, open **Insert ▸ Citation…** and click **New reference**. A reference-only entry is added to your library and ticked in the box, and the card opens for it. Type its label and reference, or build it from parts, then click **Insert** to cite it. It goes in the note's reference list like any paper. It stays in your library, listed as *reference only, no PDF*, so you can cite it in any note, attach a PDF later, or delete it.

**When you add PDFs**, a **Reference details** card opens at the bottom right, one new paper at a time. It asks for the label, the title (for its paper review heading), the APA reference and the two in-text forms. Everything saves as you type, exactly as typed. Nothing is read from the PDF or filled in for you; the label starts as the file name, as before. **Next** moves to the next paper, and × closes the card; the same fields stay on each paper's Notes & sources tab. The card doesn't take the keyboard until you click into it. Tick **Don't ask when I add PDFs** to stop it in this browser.

**In a note:**

- **Insert ▸ Citation…** Find papers and tick one or several, then choose **In brackets** or **In the sentence** (one paper). The box shows exactly what will go in. If a paper has no in-text wording yet, the box asks for it and saves it on the paper. Click a citation to open its papers, change it, or remove it. Backspace removes a citation whole.
- **Insert ▸ Reference list:** every paper cited in the note, as a list headed *References* (set like a Heading). The entries are in the note's own type (same font, size, spacing and alignment as its paragraphs) with hanging indents. Only the APA export changes the type. Place it where you like, usually at the end. Hover over it for its ×. Ctrl/Cmd+click an entry to open its paper in a new tab.
- **Citations and the list stay up to date** as you cite, uncite or change a paper's fields.

**What the app does to your wording (APA 7):**

- **Several works in one bracket:** put in reference-list order and separated by semicolons. Works by the same authors in the same order give the names once, then the years in order: undated first, in press last (§8.12).
- **Same authors, same year, both cited in the note:** a, b, c are added after the year, in the citations and the reference list, in the order of the titles, ignoring A, An and The (§8.19, §9.47). Any letter you typed is replaced by these.
- **Reference list order:**
  - letter by letter by the first author's surname (spaces, hyphens and accents ignored; "nothing precedes something"), then the initials, then the next author;
  - one author before the same author with co-authors;
  - the same authors by year, then by title (§9.44–9.49).

Nothing else is changed or added. Where something is missing, the citation shows the paper's label in red and the list says what's missing. Nothing is made up to fill the gap.

**Limits (untested, or may go wrong without warning):**

- Authors are read from the reference as "Surname, Initials," pairs. A reference written another way is ordered by whatever comes before its date.
- Numbers in group names are ordered as digits, not spelled out.
- "et al." wording that hides different authors (§8.18) isn't rewritten. A warning shows when you cite such papers together, and you then change their in-text wording.
- No page numbers or "e.g." inside brackets.
- Only works cited with Insert ▸ Citation are listed, not papers named in paper review headings.
- The note's own Export PDF prints the citations and the list as they appear on screen.

## Themes (thematic analysis)

Themes work like tags, but on passages rather than whole papers. You choose every theme and every passage; nothing is coded or suggested for you.

- **Open the Themes panel:** click **Themes** in the top bar of a paper or a note, or press **T**. It opens on the right; the pages move over to make room. Coded passages are drawn on the pages **only while the panel is open**. Close it (Themes again, the ×, or T) and they disappear from view.
- **New theme:** type a name in the panel and press Enter (or Add). Each theme gets its own colour.
- **Code a passage:** in a paper, with **Read** (V), select the words. The panel shows them under *Selected*. Click **+** beside a theme. If you type a new theme name while words are selected, the words are coded to it straight away. The same words can carry several themes; their underline shows each theme's colour in turn.
- **Change a coded passage:** with the panel open, click it on the page. You can add another theme, take one off, write a memo, copy the words or remove the coding.
- **Pull up a theme:** click a theme's name in the panel. Every passage coded to it, in every paper, is listed by paper, with your memos. In the paper you're reading, that theme's passages are drawn strongly and the others faintly.
  - **Open** goes to the spot in the PDF. Ctrl/Cmd+click or middle-click opens it in a new tab.
  - **Copy** copies the words.
  - In a note, **Insert** puts the passage in at the cursor as a Quotation, with a pin back to its page. Only the words you coded go in; no author, date or other citation text is added.
- **Themes** in the sidebar (at `#themes`):
  - **Framework matrix:** papers down the side, themes across the top. Each cell shows how many passages in that paper are coded to that theme, shaded by count within the theme, with the first passage. Click a cell to read all of them beneath the row. The bottom row gives totals, and *Include papers with nothing coded* adds the rest of the library.
  - **Codebook:** each theme's name, colour, definition (what belongs in it and what doesn't), order, number of passages and papers, and **Delete**. Delete asks once more. It takes the theme off every passage, and a passage left with no theme is uncoded along with its memo.
- **Not included:** coded passages are not in **Export PDF** and are not searched by the library search, so their memos aren't either.
- **Untested / may fail without warning:**
  - Tested in Chrome only.
  - Scanned PDFs have no words to select, so they can't be coded.
  - A selection that runs over two pages becomes one passage per page, so it counts twice.
  - Coding exactly the same words again adds the theme to the existing passage, but overlapping selections are separate passages.
  - On rotated pages the drawn boxes can be out of place, as with highlights.
  - Colours repeat after ten themes.

## Deleting a paper

Click **Delete** beside the paper in the papers list, then **Delete for good?**. It removes the paper, its table rows, annotations and its PDF from the data repository (the repository's history still has them). The same button is at the bottom of a paper's Notes & sources tab.

## To-do list (front page)

- Under the counts on the front page: **To do** and **Archive**. To do holds your own items (type one and press Enter) and, after them, every open item from the TODO stickers in your papers. Each paper item has a link to its paper and page.
- Tick an item and it moves to **Archive**, stamped with the day. Archive lists the newest first, grouped by day, with the date each item was added. Untick one to put it back. Ticking a paper's item here ticks it on the sticker too, and the other way round.
- Click your own item's text to edit it; empty it or click × to delete it. A paper's items are edited on the paper.
- Your own items are saved in `library/data.json` with everything else.

## To-do stickers

- Stick the **TODO** sticker on a page and its checklist opens: type an item and press Enter, then the next. The list shows on the page as a sticky note under the sticker.
- Tick items on that note, or click the sticker to edit, tick, remove items or add a note. *Hide the list on the page* keeps just the sticker.
- Moving the sticker moves its list; **Peel off** deletes both.
- Open items show as "2 to-dos open" on the paper in the papers list (click it to jump to the list) and in the counts at the top. They are searchable, and Export PDF lists them in the notes column as [x] / [ ].

## Linking papers to each other

- In a paper, pick **Link** (L) in the tool bar and click the spot on the page where you want the pin. Find the other paper in the list and click it, then click the spot in its PDF you mean (Esc cancels). You come back to the first paper with a small pin at that spot.
- Click a pin to open the other paper at that spot, marked for a few seconds. Hover over it to see which paper and page it points to.
- **No spot** links a paper without choosing a spot. A pin can also point to another page of the same paper.
- Click a pin to open the other paper at its spot; Ctrl/Cmd+click or the middle mouse button opens it in a new tab.
- Drag a pin to move it; with **Erase**, click it to remove it.
- The other paper's **Notes & sources → Linked from** lists the pins (and notes) pointing to it; click one to go back. **Export PDF** draws the pins and lists them in the notes column.
- On screens narrower than about 1560 px the tool bar hides the shortcut letters to fit on one row; hover over a tool to see its letter.

## Selecting, copying and highlighting text

- With **Read** (V), select text in a PDF. A small bar appears under it: **Copy**, or a **Highlight** colour. Ctrl/Cmd+C copies too.
- With **Highlight** (H), drag across words to highlight them in the chosen colour. Dragging where there is no text (a figure, the margin) draws a freehand stroke as before.
- With **Margin note** (M), select the words the note is about. They are highlighted in the note's colour and the note goes beside them in the margin; clicking the highlight opens the note, and deleting the note removes the highlight. On a scanned page with no text to select, click a line as before. Margin notes made before this are unchanged.
- Click a highlight (in Read) to see its text, add a note, change its colour, copy it or remove it. **Erase** removes it too. Highlights and their notes appear in Notes & sources and in Export PDF.
- Scanned PDFs have no text to select; use the freehand highlighter. On some two-column layouts a selection can jump across columns, because it follows the PDF's own text order.

## Table columns

- Click a column heading to rename it, change its width or short name (the label on source pins), change its type (Text, Number or Dropdown), or move it left or right.
- For a dropdown, add, rename or remove options and click the dot beside each option to cycle its colour. Renaming an option renames that value in every row once you leave the box.
- **+** at the end of the headings adds a column. **Delete column** asks twice and removes that column's values and source pins from every row.
- The Experiment column names each row, so it can only be renamed and resized.
- Source pins sit to the left of each value, in their column's colour (by position: first column ochre, second navy, and so on). A filled pin means the value is linked to its spot in the PDF. Moving a column changes its pin colour.

## Search

- Type in the search box on a tag page (All literature searches everything). It looks through the text of every PDF, plus each paper's label, reference, reading notes and annotations. Results list each matching paper with its abstract (when the PDF has a heading called "Abstract"), the matching passages with page numbers, and any of your notes that match.
- Click a passage to open the paper at that page with the word outlined. The chip at the top ("Highlighting …") turns the outlines off.
- Every word must appear in a paper for it to be listed. Put words in quotes to search for a phrase: `"eye tracking"`. Parts of words match too: `fovea` finds `foveal`.
- **First time:** the site reads the text of each PDF once and saves it to `library/text/` in the data repository. With many papers this takes a minute or two. You'll see "Reading the text of your PDFs: 3 of 40" and a commit per paper. New imports are read straight away.
- Scanned PDFs without a text layer can't be searched (only their notes can).

## Find in a paper

The box in a paper's tool bar outlines every match on every page and counts them. Press Enter (or ↓) for the next match, Shift+Enter (or ↑) for the previous, and Esc to clear. Ctrl/Cmd+F opens it while you're on the pages, because the browser's own find can't read the PDF. If you open a paper from a library search, your search words are already in the box. A phrase that wraps onto the next line in the PDF may not be found.

## Export with notes

**Export PDF** (top of each paper) downloads the paper with your annotations: the original pages, untouched and still searchable, with your pen, highlights, stickers, stickies and source pins drawn on. A column on the right lists every margin note, sticky, source pin, sticker note, to-do list and highlight note beside the spot it belongs to. A last page has your reading notes and the paper's rows from the summary table. Notes that don't fit beside their page continue on extra pages after it, and a note longer than a whole page carries on over as many pages as it needs, marked "(continued)".

Notes are set in Helvetica, which lacks some characters: Greek letters and maths signs are spelled out (α → alpha, ≈ → ~), and anything else becomes "?".

## A shorter address

GitHub Pages addresses are `https://<account>.github.io/<repository>/`, so the account name is always in it.

- **Shorter, same account:** rename the website repository (*Settings → General → Repository name*), e.g. to `library`. The address becomes `https://<account>.github.io/library/`.
- **No account name you don't want:** make a GitHub account for this work (e.g. `jyemarchant`). Create a repository there called exactly `jyemarchant.github.io`, upload the site to it and turn on Pages. The address is then just `https://jyemarchant.github.io`. Move the data repository across with *Settings → Danger Zone → Transfer ownership*, which keeps every commit. Then make a new token on the new account and enter it in the site's Settings.
- **Your own domain:** buy one (e.g. `jyemarchant.com`) and add it under *Settings → Pages → Custom domain*.

The front page has no `#…` in its address. Tag pages (`#methods`) and papers (`#paper-…`) have their own, so you can bookmark them.

## Look

A plain work layout: a sidebar, page titles at 20 px, grey hairline rules and plain labels. Nothing on the page moves by itself: no turning, blinking, flipping, pulsing or smooth scrolling. A spot you jump to is outlined (and a row you come back to is shaded) and stays still.

- **Eye photos.** Only on Home's cards. There are 26, all from Unsplash, used under the Unsplash License: free to use, no permission or credit needed (the one restriction is that you can't compile Unsplash images into a competing image service). They're loaded from Unsplash's image server, which crops each one to 3:2. Cards take photos by position, in a fixed order chosen so that cards side by side, or one above the other, don't show the same kind of animal, and no photo appears twice. A tag's photo follows its place, so adding or moving a tag shifts the photos after it. From the 27th card on, a card has a plain grey block rather than a repeated photo. The list, with each photo's Unsplash page, is in the script in `index.html` (search for `EYES`); the order is `EYE_ORDER`. If a photo can't load (offline, or blocked by a network), its card shows a grey block.
- **Logo.** Jye's eye mark with a wireframe globe for a pupil, drawn once and still, at the top of the sidebar. It's black on the light theme and the original green (`#41ff78`) on the dark theme. To change that, edit `--logo` near the top of the styles in `index.html`. The `brand` folder holds still versions: `eye.svg` (black), `eye-dark.svg` (off-white), `eye-green.svg` (green), and `eye-small.svg` and `eye-small-green.svg` with thicker lines for anything under about 40 px wide.

## Limits

- PDFs up to 50 MB each.
- Notes and pins are placed relative to the page of that PDF file. Replacing a PDF with a different edition will misplace them.
- The note editor has been tested in Chrome only; Safari, Firefox and Edge are untested. While you type with an input method that composes characters (Japanese, Chinese, some accent keys), page breaks wait until each character is finished. Lists can't be nested, and italic inside a subheading stays italic.

## Security

- The token is stored only in the browser you entered it in (local storage). Limit it to the data repository, give it an expiry date, and use **Settings → Forget token on this browser** on shared computers.
- The site loads no third-party code. It does load fonts from Google Fonts and Home's eye photos from Unsplash, so those two services see each visitor's IP address. The PDF viewer is pdf.js 3.11.174 (Apache License 2.0), bundled in `vendor/pdfjs` with its licence. Export uses pdf-lib 1.17.1 (MIT License), bundled in `vendor/pdf-lib` with its licence and loaded only when you export.
