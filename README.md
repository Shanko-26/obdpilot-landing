# OBD Pilot — Landing Page

Static pre-launch landing page for **OBD Pilot**. Pure HTML/CSS/JS, no build step.

```
index.html        ← the whole page
assets/           ← app screenshots + icon
.nojekyll         ← tells GitHub Pages to serve files as-is
CNAME             ← (add this when you connect a custom domain)
```

## Run locally

Just open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```

## Deploy to GitHub Pages

1. Create a GitHub repo and push this folder.
2. Repo **Settings → Pages → Build and deployment → Source: Deploy from a branch**,
   branch `main`, folder `/ (root)`. Save.
3. Live in ~1 min at `https://<user>.github.io/<repo>/`.

## Custom domain (GoDaddy)

1. Buy the domain on GoDaddy.
2. Add a file named `CNAME` to this repo containing just your domain, e.g. `obdpilot.app`.
3. In **GoDaddy → DNS**, point the domain at GitHub Pages:
   - **Apex** (`obdpilot.app`): four `A` records →
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - **www**: one `CNAME` record → `<user>.github.io`
4. In GitHub **Settings → Pages**, set the custom domain and tick **Enforce HTTPS**
   (wait a few minutes for the cert).

## Collecting emails

The "Notify me at launch" forms currently just confirm to the visitor — nothing is
stored. To actually capture addresses, set `FORM_ENDPOINT` near the bottom of
`index.html` to a form backend URL (e.g. a free [Formspree](https://formspree.io) form).

## Before going fully live

- Drop a real OBD-II adapter photo into the Compatibility section (placeholder slot).
- Swap the beta-driver testimonials for real ones.
- Point the footer **Privacy Policy** / **Terms of Service** links (`#`) at real pages.
