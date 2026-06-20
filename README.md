# Moliki Studio — Interior Design Website

A single-page static website for an interior design business. Pure HTML/CSS/JS, no build step, no dependencies — works on GitHub Pages out of the box.

## Run locally

Just open `index.html` in a browser, or serve it:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Deploy to GitHub Pages

1. Create a new repo on GitHub (e.g. `moliki-studio`).
2. Push this folder to it:
   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/moliki-studio.git
   git push -u origin main
   ```
3. In the repo, go to **Settings → Pages**.
4. Under **Source**, select the `main` branch and `/ (root)` folder, then save.
5. GitHub will publish the site at `https://<your-username>.github.io/moliki-studio/` within a minute or two.

## Contact form setup (Web3Forms)

The contact form sends submissions straight to your email via [Web3Forms](https://web3forms.com) — free, no backend required.

1. Go to https://web3forms.com and enter the email address you want submissions sent to. You'll instantly receive an **access key** by email (no account/login needed).
2. Open `index.html` and find this line (inside the `<form id="contact-form">` block):
   ```html
   <input type="hidden" name="access_key" value="YOUR_WEB3FORMS_ACCESS_KEY">
   ```
3. Replace `YOUR_WEB3FORMS_ACCESS_KEY` with the key you received.
4. Save and redeploy (see below). Test by submitting the form on your live site — you should get an email within seconds.

The key is safe to expose in client-side code; Web3Forms is designed for this (it only allows submissions, not reading your data).

## Deploy to your existing GitHub repo

From this folder:

```bash
git add index.html README.md
git commit -m "Connect contact form to Web3Forms"
git push
```

If GitHub Pages is already enabled on this repo, the live site updates automatically within a minute or two of the push. If it's not enabled yet:

1. Go to your repo on GitHub → **Settings → Pages**.
2. Under **Source**, select your branch (usually `main`) and `/ (root)`, then save.
3. Your site will be live at `https://<your-username>.github.io/<repo-name>/`.



- **Business name / copy**: edit the text directly in `index.html` (logo, hero headline, about section, etc).
- **Colors**: all defined as CSS variables at the top of the `<style>` block (`--plaster`, `--clay`, `--walnut`, etc.) — change once, updates everywhere.
- **Portfolio images**: the portfolio grid currently uses abstract SVG placeholders. Swap a `<svg>` block for a real `<img src="images/your-photo.jpg">` tag once you have project photography.
- **Contact form**: connected to Web3Forms — see setup section above. To swap providers (e.g. Formspree), replace the fetch URL and form field names in the `<script>` block at the bottom of `index.html`.

## Structure

```
interior-site/
├── index.html   # everything — markup, styles, and scripts in one file
└── README.md
```
