# Hotel Nature Valley Website

A modern, responsive static website for Hotel Nature Valley, Dalhousie, Himachal Pradesh.

**Live Site:** [naturevalley.in](https://naturevalley.in)

---

## Tech Stack

- **HTML5** — Semantic, accessible markup
- **CSS3** — Custom properties, Flexbox, Grid, animations
- **Vanilla JavaScript** — No frameworks, zero dependencies
- **Google Fonts** — Playfair Display, Inter, Cormorant Garamond

### Why Vanilla Stack?

1. **Zero dependencies** — No npm, no build tools, no maintenance overhead
2. **Easy deployment** — Works on any static host
3. **Fast loading** — No framework overhead (~50KB total)
4. **Easy maintenance** — Edit HTML directly, no compile step

---

## Quick Start

### Local Development

```bash
# Option 1: Python (macOS/Linux)
python3 -m http.server 8080

# Option 2: Node.js
npx serve

# Option 3: PHP
php -S localhost:8080

# Then open http://localhost:8080
```

### Deployment

The site is pure static files. Deploy to any static host:

- **GitHub Pages** — Push to `gh-pages` branch
- **Netlify** — Drag & drop the folder
- **Vercel** — Connect repo or drag & drop
- **Any web host** — Upload via FTP

---

## Project Structure

```
static-web/
├── index.html          # Main website (single page)
├── css/
│   └── styles.css      # All styles (design system + components)
├── js/
│   └── main.js         # Interactivity (nav, animations, lightbox)
├── images/
│   ├── hero/           # Hero video/images
│   ├── rooms/          # Room photos
│   ├── attractions/    # Local attractions
│   ├── gallery/        # Property gallery
│   └── icons/          # Logo, favicon
├── asset/              # Original source images
└── README.md           # This file
```

---

## Updating Content

### Change Text Content

1. Open `index.html` in any text editor
2. Find the section you want to change
3. Edit the text between HTML tags
4. Save and refresh browser

### Replace Images

1. Add new image to appropriate `images/` subfolder
2. Update the `src` attribute in `index.html`
3. Keep images under 500KB for fast loading

### Update Contact Info

Search for these in `index.html`:
- Phone: `+91 97796 16655`
- Email: `info@naturevalley.in`
- Address: `Hotel Nature Valley, Dalhousie Road...`

### Change Colors

Edit CSS custom properties at the top of `css/styles.css`:

```css
:root {
  --color-primary: #2D5A3D;     /* Main green */
  --color-accent: #C9A962;      /* Gold buttons */
  --color-text: #1A2A1F;        /* Body text */
}
```

---

## Booking System

The "Book Now" buttons link to the RevCatalyst booking engine:
```
https://hotel-nature-valley.revcatalyst.in
```

To change the booking URL, search & replace this URL in `index.html` (and the legal pages).

---

## Live Google Reviews

The reviews section can pull **live Google reviews** (author, star rating, date,
text, and a link to the review) directly from the Google Places API — no backend
needed, it runs in the browser.

### Setup (one time)

1. Go to [Google Cloud Console](https://console.cloud.google.com/) → create/select a project
2. Enable **Places API (New)**
3. Create an **API key**, then restrict it:
   - Application restriction: **HTTP referrers** → `naturevalley.in/*` (and `localhost/*` for testing)
   - API restriction: **Places API (New)** only
4. Open `js/main.js` and paste the key into:
   ```js
   const GOOGLE_PLACES_API_KEY = ''; // <-- paste here
   ```

The Place ID is already configured (`ChIJjSkiRZSRHDkRQWExem6_c6k` = Hotel Nature Valley, Banikhet).

**Fallback:** if no key is set (or the API call fails), the static review cards
in `index.html` are shown instead — the site never breaks.

---

## Social & Maps Links

- Instagram: `https://www.instagram.com/hotelnaturevalley/`
- Facebook: `https://www.facebook.com/officialhotelnaturevalley`
- WhatsApp: `https://wa.me/919779616655`
- Google Maps listing / directions: `https://maps.app.goo.gl/u1JR2USoAEathQ8X8`

---

## Contact & Wedding Forms

The site is static (no server), so both forms deliver enquiries via **WhatsApp**:
on submit, a WhatsApp chat to **+91 97796 16655** opens with all form details
pre-filled — the visitor just presses send. To use email delivery instead,
sign up at [Formspree](https://formspree.io) (free) and point the forms at
your Formspree endpoint in `js/main.js`.

---

## Image Optimization Tips

For best performance:

1. **Resize large images** — Max 1920px width
2. **Compress** — Use [Squoosh](https://squoosh.app) or [TinyPNG](https://tinypng.com)
3. **Use JPEG** — For photos (80% quality)
4. **Use WebP** — For modern browsers (even smaller)

---

## Browser Support

✅ Chrome (last 2 versions)  
✅ Firefox (last 2 versions)  
✅ Safari (last 2 versions)  
✅ Edge (last 2 versions)  
✅ Mobile Safari (iOS 14+)  
✅ Chrome Mobile (Android 8+)

---

## License

© 2024 Hotel Nature Valley. All rights reserved.
