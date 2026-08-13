# Haji Mukhtar Properties & Petroleum — Website

A single, self-contained `index.html`. No build step, no framework — Tailwind is
already compiled and inlined, so it loads instantly on GitHub Pages. The only
external calls are Google Fonts and the placeholder Unsplash images.

## Deploy on GitHub Pages
1. Create a repository (e.g. `haji-mukhtar-site`).
2. Add `index.html` to the root of the `main` branch and push.
3. Repo → **Settings → Pages** → Source: **Deploy from a branch** → Branch:
   `main` / `/ (root)` → **Save**.
4. Your site goes live at `https://<username>.github.io/<repo>/` within a minute.
5. **Custom domain — hajimukhtar.com**: Settings → Pages → **Custom domain** →
   enter `hajimukhtar.com` → Save. GitHub will add a `CNAME` file to the repo
   automatically. At your DNS provider, point the domain at GitHub Pages:
   - Four **A** records on the apex (`@`) → `185.199.108.153`, `185.199.109.153`,
     `185.199.110.153`, `185.199.111.153`
   - A **CNAME** record for `www` → `<username>.github.io`
   Then tick **Enforce HTTPS** once the certificate provisions (can take a few
   hours after DNS propagates).

## Swap the placeholder photography (biggest credibility lever)
Open `index.html` and search for **`data-img=`**. Each image tag has an ID:

| ID              | Where it appears                    |
|-----------------|-------------------------------------|
| `HERO_GROUP`    | Rotating hero — slide 1 (The Group) |
| `HERO_RE`       | Rotating hero — slide 2 (Real Estate)|
| `HERO_PE`       | Rotating hero — slide 3 (Petroleum) |
| `RE_HERO`       | Split showcase — Real Estate half   |
| `PE_HERO`       | Split showcase — Petroleum half     |
| `PROJ_BAHARINI` | Baharini card                       |
| `PROJ_TUDOR`    | Tudor Pearl card                    |
| `PROJ_JAMEEL`   | Jameel Prime card                   |
| `PE_BAND`       | Wide petroleum band                 |
| `SUSTAIN`       | Sustainability section image        |
| `COMPANY`       | Company section image               |

Replace the `src="..."` with your real renders / drone shots. Each image sits
over an on-brand gradient, so the layout never breaks while photos load or if a
URL is wrong. Keep files reasonably sized (≈1400–1600px wide) for fast loads.

## Wire up the "Request the data room" form
The form currently uses a placeholder. Until you set a real endpoint, submitting
opens the visitor's email client addressed to `investors@hajimukhtar.co.ke`.

To collect submissions on a static site, use a form service (e.g. Formspree):
1. Create a form there and copy your endpoint.
2. In `index.html`, find `action="https://formspree.io/f/your-form-id"` and
   replace it with your real endpoint. That's it — the mailto fallback switches
   off automatically once the placeholder text is gone.

## The founder's portrait
The founder's photo (nameplate edited off the desk) is already **embedded
directly in `index.html`** — nothing extra to upload, and it shows even if the
site is opened as a single file. A standalone `founder-portrait.jpg` is also
included in case you want it for the deck, profile, or other materials. To swap
the photo later, either replace `founder-portrait.jpg` and re-embed, or point the
founder `<img src>` at an external file. The signature is set in a script font;
replace the `Abdi Mukhtar Mohamed` line with an `<img>` if you have a scanned one.
The title currently reads "Founder" — edit if you use a fuller title.

## Placeholders still to update
- Domain (`hajimukhtar.com`) and email (`investors@hajimukhtar.com`) are now
  set throughout the site — just make sure your mail provider is configured to
  actually receive mail at that address before launch.
- "Delivered projects available on request" — swap for a delivered-projects
  section once you have names and photos.

## Notes
- **Page structure** (modelled on a diversified-group site): rotating division
  hero → What We Do → the split-screen showcase → Real Estate → Petroleum →
  Sustainability → The Group → Investor data room → footer.
- **Rotating hero** auto-advances every 6s, pauses on hover/focus, has prev/next
  arrows and dots, and stops auto-advancing when "reduce motion" is set.
- **Social links** in the footer are placeholders (`href="#"`) — replace with your
  real LinkedIn / Instagram / X profiles.
- **Sustainability** copy is intentionally general (no specific programs or figures
  are claimed) — expand it as real initiatives begin.
- Accessibility floor is built in: keyboard focus rings, reduced-motion support,
  alt text, skip-to-content link, mobile menu and carousel ARIA.
- Gold-on-black is used only for large display type and labels; body copy stays
  ivory for contrast. Keep that split if you add content.
