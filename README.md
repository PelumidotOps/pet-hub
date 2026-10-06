# PetHub

Standalone copy of the existing live website, separated from Deborah's portfolio. HTML, inline CSS/JavaScript, and local images were recovered from the published website because the supplied GitHub repository does not contain this project's source.

## Run locally

Install Node.js 22 or newer. No npm dependencies are required.

```bash
npm run dev
```

Open http://localhost:3000. Use another port with `PORT=3001 npm run dev` on macOS/Linux or `$env:PORT=3001; npm run dev` in PowerShell.

## Build

```bash
npm run build
```

The build copies `public/` into `dist/`. No API keys or environment variables are required for the current front end.

## Push to its own GitHub repository

Extract this ZIP, open the `pet-hub` folder, and create an empty GitHub repository named `pet-hub` (without an initial README).

```bash
git init
git add .
git commit -m "Initial standalone PetHub website"
git branch -M main
git remote add origin https://github.com/blackdebbie/pet-hub.git
git push -u origin main
```

## Deploy separately to Vercel

Import that GitHub repository as a new Vercel project. Set framework preset to **Other**, root directory to the repository root, build command to `npm run build`, and output directory to `dist`. `vercel.json` supplies the build settings. Deploy. The homepage is `/`, and existing `.html` page URLs remain available.

## Pages included

- `/case-studies/adopt.html`
- `/case-studies/book.html`
- `/case-studies/case-study-6.html`
- `/case-studies/contact.html`
- `/case-studies/grooming.html`
- `/case-studies/service.html`
- `/case-studies/signup.html`
- `/case-studies/store.html`

## Existing behavior and dependencies

Sign-in is a localStorage demonstration, not real account authentication. Appointment confirmation is a browser modal; bookings are not sent or stored on a server. The calendar is the original fixed May 2025 demo. Store/adoption buttons and contact forms retain their original demo behavior.

External Google Fonts, icon libraries, and Unsplash/avatar image URLs remain as in the original website and require internet access. All discovered local page and image dependencies are bundled. This package does not include a server, database, payment integration, or hidden application source.

## Validation

- Static build completed.
- All internal HTML navigation and image references resolve to included files.
- 25 inline JavaScript blocks passed Node syntax checks.
- Interactive browser verification was unavailable in this environment; test mobile navigation, forms, and external assets in a Vercel preview before using with clients.

See `SOURCE-NOTES.json` for the recovered file inventory and source URL.
