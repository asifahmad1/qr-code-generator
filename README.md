# QR Code Generator — Links, Wi-Fi, Contacts & More

Create real, scannable QR codes — **100% in your browser**. No uploads, no sign-up, no tracking codes: the content you type is encoded directly into the pattern, on your device.

**▶ Live on Asif SaaS Studio:** open the tools catalogue and choose *QR Code Generator* (slug `qr-code-generator`).

## What it does — you decide the fields
Pick a content type, fill in its fields, generate, download:

- **Text** — any free text
- **Website** — a URL (`https://` added automatically if omitted)
- **Wi-Fi** — SSID, security (WPA/WEP/open), password, hidden-network flag → phones join on scan
- **Contact card** — name, organisation, title, phone, email, website, address, note → vCard 3.0
- **Email** — recipient, subject, message → `mailto:`
- **SMS** — number + message · **Phone** — number · **Location** — latitude/longitude

Every field is validated (required fields, email/phone formats, coordinate ranges, URL parsing), and a live preview shows the exact encoded content as you type. Output: QR versions 1–20 chosen automatically, error-correction L/M/Q/H, downloads as PNG (256–2048 px) or sharp-at-any-size SVG.

The QR encoder is written from ISO/IEC 18004 inside the page — Reed–Solomon error correction over GF(256), block interleaving, spec penalty-rule mask selection. No libraries, no backend, no API keys.

## Use
Open `index.html` in any modern browser — or from this repo via any static host. No build step, no dependencies.

- Single file, **41.6 KB**, all CSS/JavaScript inline
- No localStorage, no service workers, no browser permissions, no parent-window access — safe in a sandboxed iframe
- Responsive layout in the Asif SaaS Studio emerald + lime branding

## Testing
31/31 payload-builder and validation tests passed (Node.js, against the shipped code), and 15/15 generated codes — versions 1–20, all error-correction levels, Wi-Fi/vCard/geo/mailto and UTF-8 payloads — were **decoded back to the exact original content by ZXing**, the industry-standard barcode engine. Full report: `qr-code-generator-test-report.md`. Complete documentation: `docs/qr-code-generator-docs.pdf`.

Created by Dr. Asif Ahmad · Asif SaaS Studio · v1.0
