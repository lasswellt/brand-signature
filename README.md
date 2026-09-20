# Brand Properties Email Signature Generator

A single-file, offline HTML tool that produces a consistent Brand Properties email
signature. Fill in your details, check the preview, copy it into your mail client.
No build step, no dependencies, no network calls — open the file in a browser.

## Use it

Open `signature.html` (or `signature-v2.html`) in any browser.

1. **Your details** — name, title, tagline, two address lines, and direct, mobile,
   office and fax numbers. Blank fields are omitted from the output rather than
   left as empty rows.
2. **Check the preview** — it renders live as you type.
3. **Copy** — two buttons:
   - **Copy signature** puts the formatted signature on the clipboard. Paste this
     straight into Gmail, Outlook or Apple Mail.
   - **Copy code (for signature tools)** puts the raw HTML on the clipboard, for
     admin consoles and signature-management platforms that expect markup.

The page includes paste instructions for each mail client.

## Which file

| File | What it is |
|---|---|
| `signature.html` | v1 generator — italic tagline treatment |
| `signature-v2.html` | v2 generator — uppercase tagline treatment |
| `signature-bare.html` | v1 signature markup only, no generator UI — for pasting into a tool and editing by hand |
| `signature-v2-bare.html` | v2 signature markup only |
| `signature-corrected.html` | Fixed-content v1 signature, no form |

`fonts/` holds self-hosted Montserrat (400/500/700) so the page renders identically
without calling out to Google Fonts. `logo-header*.png|svg` are the wordmark at
several resolutions.

## Compatibility notes

The signature is table-based with inline styles, which is what email clients
actually support. A few specifics worth knowing if you edit it:

- An MSO conditional block sets `AllowPNG` and 96 DPI so Outlook on Windows does
  not resample the logo.
- The favicon is an inline SVG data URI, so the page never requests
  `/favicon.ico` and works fully offline.
- Muted text is `#4b5563` rather than a lighter gray, to stay comfortably within
  AA contrast at small sizes.

Brand palette: navy `#01426A`, accent `#963821`.
