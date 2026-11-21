# RFP Document Generator

Frontend-only web app that completes an RFP Word template with project details.
No backend, no database, no cloud storage: everything runs and is stored in the browser.

- `index.html` – the whole app (single file; the RFP template is embedded as base64)
- `template/` – the original Word draft the app was built from
- Libraries (JSZip, docx-preview, html2pdf.js) load from cdnjs; project data is never sent anywhere.

## Use
Open `index.html` in a browser (or publish with GitHub Pages: Settings → Pages → GitHub Actions).
Workflow: Load template → Enter details → Review missing info → Generate → Download Word/PDF.

## Security notes
Saved drafts can be encrypted with a passphrase (PBKDF2 + AES-GCM). Without one they are stored as plain text in
localStorage. Exported .docx/.pdf/.json files are not encrypted. No software is completely immune to attack.
