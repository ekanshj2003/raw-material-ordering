# Raw Material Ordering — Mumuksh Impex LLP

A single-page web app for planning raw material purchases.

- **Products & BOM** — BOM per 1 piece in grams (GSM × width m × length m for sheets, direct grams for SAP/pulp/glue/elastic), paste straight from the Excel BOM sheet, with each material's vendor, rate and **opening stock**.
- **Plan order** — pick products, enter monthly production. The app calculates
  `required kg = production × grams per piece × (1 + wastage%) ÷ 1000`, subtracts opening stock, rounds up,
  and groups the result into one purchase order per vendor in the company PI format (PO numbering continues from 123).
- **Copy for Excel** pastes a PO straight into the PI workbook; **Print / PDF** prints it.
- **Materials & stock**, **Vendors**, **Setup & backup** (factories, next PO number, backup/restore).

## Login
The first time the app opens in a browser it asks you to create an **admin** username and 4–6 digit PIN. The admin adds staff users and resets PINs in *Setup & backup → Users*. Staff can enter BOMs and make orders; only admins manage users and restore backups. Users are included in the backup file. The login keeps casual users out on a shared computer; it is not a substitute for locking the computer.

Data is stored in the browser (localStorage). Use *Setup & backup → Download backup file* regularly and *Restore* to move data to another computer.

## Works on every device
Runs in any modern browser: iPhone/iPad (Safari), Android (Chrome), Windows, Mac and Linux. It can be installed like an app and keeps working offline.
- **iPhone / iPad:** open the link in **Safari** → tap **Share** → **Add to Home Screen** → **Add**.
- **Android:** open in **Chrome** → menu **⋮** → **Add to Home screen** / **Install app**.
- **Windows / Mac (Chrome or Edge):** click the install icon at the right of the address bar.

## Hosting on GitHub Pages
1. Create a new repository (e.g. `rm-ordering`) and upload **all files** from this folder: `index.html`, `manifest.webmanifest`, `sw.js`, the four `.png` icons and this `README.md`.
2. Repository **Settings → Pages → Source: Deploy from a branch**, branch `main`, folder `/ (root)`.
3. The app will be live at `https://<your-username>.github.io/rm-ordering/`.

> Keep the repository **private** if vendor rates are confidential (GitHub Pages on private repos needs a paid plan), or host it internally.
