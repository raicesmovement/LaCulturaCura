# La Cultura Cura: Somos Medicina
**Third Annual Community Wellness Gathering**
May 30, 2026 · Lugo Elementary School, Lynwood CA

---

## Deploying to GitHub Pages

### First time setup (5 minutes)

1. **Create a GitHub account** at github.com if you don't have one.

2. **Create a new repository**
   - Click the green **New** button
   - Name it: `la-cultura-cura` (or any name you like)
   - Set it to **Public**
   - Click **Create repository**

3. **Upload the file**
   - Click **Add file → Upload files**
   - Drag and drop `index.html` into the window
   - Scroll down and click **Commit changes**

4. **Enable GitHub Pages**
   - Go to your repo → **Settings** → **Pages** (left sidebar)
   - Under **Source**, select **Deploy from a branch**
   - Branch: **main** · Folder: **/ (root)**
   - Click **Save**

5. **Your site is live** in ~60 seconds at:
   `https://YOUR-GITHUB-USERNAME.github.io/la-cultura-cura/`

---

## Connecting a custom domain (optional)

If you have a domain (e.g. `laculturacura.org`):

1. In your domain registrar (Porkbun, GoDaddy, etc.), add these DNS records:
   ```
   Type: A     Name: @    Value: 185.199.108.153
   Type: A     Name: @    Value: 185.199.109.153
   Type: A     Name: @    Value: 185.199.110.153
   Type: A     Name: @    Value: 185.199.111.153
   Type: CNAME Name: www  Value: YOUR-USERNAME.github.io
   ```
2. In GitHub → Settings → Pages → Custom domain: enter your domain
3. Check **Enforce HTTPS**
4. DNS may take up to 48 hours to propagate

---

## Things to update before going live

Open `index.html` in any text editor and find these spots:

| What to update | How to find it |
|---|---|
| Registration link (Eventbrite, etc.) | Search: `Register to Attend` — update the `href` on that button |
| Contact email / form backend | Search: `handleSubmit` — replace `alert()` with your Formspree or Google Form action |
| Survey links (pre & post) | Search: `survey-placeholder` — swap in your Google Form URL |
| Testimonials | Search: `Community participant, 2025` — replace with real quotes |
| Organizer contact info | Add to footer if desired |
| Banner image | Add `<img src="banner.png" ...>` at the top of the hero section |

### Adding your banner image

1. Upload `Final_LA_CULTURA_CURA_Banner_-_2.png` to your GitHub repo alongside `index.html`
2. In `index.html`, find the hero section and add before the closing `</div>` of hero-inner:
   ```html
   <img src="Final_LA_CULTURA_CURA_Banner_-_2.png"
        alt="La Cultura Cura Festival: Somos Medicina"
        style="max-width:100%;border-radius:12px;margin-bottom:2rem;">
   ```

### Connecting a form backend (free options)

**Formspree** (easiest — free up to 50 submissions/month):
1. Go to formspree.io → create account → New Form
2. Copy your form ID (looks like `xpzgkwqr`)
3. In `index.html`, find `handleSubmit` and replace the `alert()` block with:
   ```javascript
   fetch('https://formspree.io/f/YOUR_FORM_ID', {
     method: 'POST',
     body: new FormData(e.target),
     headers: { 'Accept': 'application/json' }
   }).then(() => alert(msgs[type][lang]));
   ```
   Use separate form IDs for each of the three tabs if you want separate inboxes.

---

## Making updates

To update content after launch:
- Go to your GitHub repo
- Click on `index.html`
- Click the **pencil icon** (Edit)
- Make your changes
- Click **Commit changes**

The site updates automatically within ~30 seconds.

---

## File structure
```
la-cultura-cura/
├── index.html          ← the entire site (single file)
├── README.md           ← this file
└── (optional) banner.png or other images
```

---

*Built with cultural integrity for the community, by the community.*
*La Cultura Cura: Somos Medicina — Return to Our Roots*
