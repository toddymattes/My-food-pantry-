# My Food Pantry — Canned Food Inventory

## Features
- Phone-camera barcode scanning for UPC-A, UPC-E, EAN-13 and EAN-8 where supported by the browser.
- Barcode lookup against Open Food Facts to suggest a product name.
- Automatically opens Add Food with the scanned barcode prefilled when the barcode is not in your inventory.
- Add cans, search by food name or barcode, and subtract one with Use 1.
- Inventory persists in this browser on this device using local storage.
- Installable PWA when hosted over HTTPS.

## Run it
Camera access requires a secure context (HTTPS, or localhost). Upload this folder to a static HTTPS host (for example GitHub Pages, Netlify, or your own web host), then open the site in Chrome on your phone and grant camera permission. Use the browser menu's **Add to Home screen** / **Install app** option.

For local testing on a computer, run a local web server from this folder and open it at `http://localhost`.

## Notes
- Automatic scanning depends on browser support for the Barcode Detection API. If unavailable, use the manual barcode field.
- Product names are suggested by Open Food Facts and may be missing or inaccurate; confirm the name before saving.
- Inventory is stored only in this browser on this device. Clearing browser site data can erase it. This first version has no cloud sync or account backup.
