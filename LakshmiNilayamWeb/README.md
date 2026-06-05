# Lakshmi Nilayam — Website

## Folder Structure (GitHub)

```
lakshmi-nilayam/          ← root of your GitHub repository
├── index.html
├── style.css
├── script.js
├── images/               ← create this folder, add your photos here
│   ├── exterior.jpg      ← Building exterior / entrance
│   ├── living-room.jpg   ← Living & dining area
│   ├── bedroom.jpg       ← Master bedroom
│   ├── kitchen.jpg       ← Modular kitchen
│   ├── bathroom.jpg      ← Bathroom
│   ├── garden.jpg        ← Garden / terrace / common area
│   └── parking.jpg       ← Parking area
└── README.md
```

---

## How to add your photos

### Flat section (4 room cards)
In `index.html`, find each `.flat-card`. You'll see a comment like:
```html
<!-- Image path: images/bedroom.jpg -->
<div class="flat-image-placeholder">...</div>
```
Replace those two lines with:
```html
<img src="images/bedroom.jpg" alt="Bedroom" />
```

### Gallery carousel (7 slides)
In `index.html`, find comments like:
```html
<!-- To add image: replace the div below with:
     <img src="images/exterior.jpg" alt="Building Exterior" class="slide-img" />
-->
<div class="slide-placeholder" ...>...</div>
```
Delete the `<div class="slide-placeholder">` block and paste the `<img>` tag in its place.

In `style.css`, uncomment this line (remove the `/* */`):
```css
/* .slide-img { width: 100%; height: 520px; object-fit: cover; display: block; } */
```

---

## Recommended image sizes
| Image | Recommended size |
|-------|-----------------|
| Carousel slides | 1400 × 520 px (landscape) |
| Flat room cards | 800 × 400 px |
| General | JPEG, 80–90% quality, under 300 KB each |

Use [Squoosh](https://squoosh.app) (free, in-browser) to compress before upload.

---

## Map embed — update to your exact building pin

1. Open [Google Maps](https://maps.google.com)
2. Search for your building or drop a pin at the exact location
3. Click **Share → Embed a map → Copy HTML**
4. In `index.html`, find the `<iframe>` inside `.map-embed` and replace the entire `src="..."` value with the one from Google

---

## Deploy on Render (free static site)

### One-time setup

1. Push this folder to a **public GitHub repository**
   ```
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/lakshmi-nilayam.git
   git push -u origin main
   ```

2. Go to [render.com](https://render.com) → **New → Static Site**

3. Connect your GitHub account and select the `lakshmi-nilayam` repository

4. Fill in:
   - **Name:** lakshmi-nilayam (or any name)
   - **Branch:** main
   - **Root Directory:** *(leave blank — files are at repo root)*
   - **Build Command:** *(leave blank — no build needed)*
   - **Publish Directory:** `.`   ← just a dot

5. Click **Create Static Site**

Render will deploy in ~1 minute and give you a free URL like:
`https://lakshmi-nilayam.onrender.com`

### Updating the site later
Just push changes to GitHub — Render auto-deploys on every push to `main`.

---

## Custom domain (optional)
In Render dashboard → your site → **Settings → Custom Domains** → add your domain (e.g. `lakshminilaayam.in`).
Then update your domain registrar's DNS to point to Render's servers as instructed.
