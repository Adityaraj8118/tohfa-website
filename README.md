# Tohfa Restaurant & Bar Website

Website for Tohfa Restaurant & Bar, an Indian restaurant and bar in Bukoto, Kampala. It has two pages: a home page with the restaurant's details, services and venue information, and a full menu page with prices in UGX. Orders and bookings go through WhatsApp with a pre-filled message.

**Live site:** https://adityaraj8118.github.io/tohfa-website/

**Status:** Draft. The site is live on GitHub Pages, but some content is still placeholder (see [Current limitations](#current-limitations)).

## Pages

### Home (`index.html`)

- Hero section with a rotating set of dish photos.
- Open/closed status calculated from Kampala time (UTC+3), based on opening hours of 8 AM to midnight.
- Offer banner that shows only between a start and end date, then hides itself.
- "Today's specials" section.
- Facilities (parking, Wi-Fi, kids' play area and others) and an occasions list. Tapping an occasion opens WhatsApp with a message for that event type.
- Ordering options: dine in, takeaway, delivery and WhatsApp.
- Menu preview with tabs for Indian, Indo-Chinese, Breakfast & Café, Ugandan & Grill and Drinks.
- Party halls, whole-venue booking, the bar, and a tiffin (meal plan) section.
- Address, hours, payment options, Google Maps link, and copy-to-clipboard buttons for the phone number and email.

### Menu (`menu.html`)

- 331 dishes and drinks in 9 sections: Breakfast & Snacks, Soups, Starters, Indian Mains, Rice & Breads, Indo-Chinese, Ugandan & Continental, Combos & Platters, and Drinks.
- Search across dish names and descriptions.
- Veg / non-veg filter.
- An "Order on WhatsApp" button on each dish.
- Tap a dish photo to view it larger.

## Tech stack

- HTML, CSS and vanilla JavaScript. No framework, build step or package manager.
- Fonts: Fraunces and Manrope from Google Fonts.
- Dish photos: loaded from Unsplash by URL.
- Hosting: GitHub Pages, served from the repository root.

## Project structure

```
tohfa-website/
├── index.html    # Home page (markup, styles and scripts in one file)
├── menu.html     # Full menu page; menu data is a JSON object in the page script
├── .nojekyll     # Tells GitHub Pages to serve files as-is, without Jekyll
├── backup/       # Earlier versions of both pages, kept for reference
└── README.md
```

## Running locally

No installation is needed. Open `index.html` in a browser, or serve the folder so links between pages behave the same as on GitHub Pages:

```bash
git clone https://github.com/Adityaraj8118/tohfa-website.git
cd tohfa-website
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Updating content

All content is in the two HTML files.

| What to change | Where |
|---|---|
| Menu items and prices | The `MENU` object in the script section of `menu.html` |
| Menu preview on the home page | The `MENU` object in the script section of `index.html` (a separate, shorter list; keep prices in sync with `menu.html`) |
| Offer banner | The `OFFER` object (`title`, `text`, `start`, `end`) in **both** `index.html` and `menu.html`. Dates use `YYYY-MM-DD` in Kampala time. |
| Opening hours shown as open/closed | The open/closed script in `index.html` (currently 8 AM to midnight) |

## Current limitations

- Dish photos are stock images from Unsplash, not photos of the restaurant's own food. The site says so on both pages.
- "Today's specials" shows four sample dishes. It is not connected to any data source yet and has to be edited by hand.
- The menu data lives inside `menu.html`, and the home page preview is a separate copy, so a price change has to be made in both places.
- There is no online payment or order system. Orders are completed over WhatsApp.
