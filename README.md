# ReWear — Clothing Exchange & Swap Marketplace

A responsive frontend prototype for a sustainable clothing barter marketplace. Built with HTML, CSS, and vanilla JavaScript so it can be deployed directly to GitHub Pages.

## Features
- Responsive marketplace UI with sample clothing listings
- Search by name, category, description, owner, and location
- Filters for category, size, condition, and location
- Create and save a clothing listing (optional image URL)
- Send swap requests with an offer/message
- View, accept, or decline demo swap requests
- Save favourite listings
- Estimated swap value shown for every listing
- Demo admin panel for listing moderation and request counts
- Browser `localStorage` persistence
- Accessible labels, keyboard Escape-to-close modals, empty states, and mobile layout

## Run locally
1. Download or clone this folder.
2. Open `index.html` in a modern browser. No build step is required.
3. For a local web server, run `python3 -m http.server 8000` from this directory and open `http://localhost:8000`.

## Deploy to GitHub Pages
1. Create a public GitHub repository, for example `rewear-clothing-swap`.
2. Upload `index.html`, `style.css`, `script.js`, `README.md`, and `PROJECT_REPORT.md` to the repository root.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, select **Deploy from a branch**, choose `main` and `/ (root)`, then save.
5. Wait for the Pages deployment and open the URL GitHub provides, typically `https://YOUR-USERNAME.github.io/rewear-clothing-swap/`.

## Important limitations
This is a frontend-only academic prototype. Data is saved only in the current browser using localStorage; it is not shared between users or devices. There is no real authentication, database, private chat, email notification, courier integration, server-side admin security, or automated matching. Image URLs are loaded from the internet; the interface includes a fallback image. Do not enter sensitive personal data. A production version would need a backend/API, database, authentication, authorization, moderation, secure messaging, and privacy safeguards.

## Submission checklist
- GitHub repository link: create and upload the project using the steps above.
- Detailed project report link: upload/share `PROJECT_REPORT.md` (or convert it to PDF).
- Deployed project link: enable GitHub Pages and use the published URL.
- Feedback video link: record a short screen recording using `FEEDBACK_VIDEO_SCRIPT.md`, upload it to a video host or Drive, set access so evaluators can view it, and submit the share URL.
