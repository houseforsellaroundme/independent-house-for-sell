# 2 BHK Independent House for Sale – Tadepalligudem

A single-page, mobile-first landing page for an owner-listed **2 BHK independent house** in **Karri Satyavathi Nagar, Tadepalligudem, West Godavari, Andhra Pradesh** (asking price ₹32 lakh).

The entire site is one self-contained HTML file with inline CSS and vanilla JavaScript. There is no build step, no framework and no dependencies to install.

---

## Property at a Glance

| Item | Detail |
|---|---|
| Type | Independent house, 2 BHK |
| Locality | Karri Satyavathi Nagar, Tadepalligudem |
| Price | ₹32 lakh |
| Built-up area | 1,100 sq ft |
| Plot size | 2.88 cents |
| Bathrooms | 2 |
| Facing | East (north-east entrance) |
| Parking | 1 vehicle |
| Water | Borewell |
| Age | Approx. 8 years |
| Seller | Owner (no broker) |

---

## Features

- **Hero section** with price, key highlights and call / WhatsApp / enquiry buttons
- **Glassmorphism dark theme** with a slow animated background (respects `prefers-reduced-motion`)
- **Responsive layout** for phones, tablets and desktops, including safe-area support for notched devices
- **Slide-in mobile menu** with overlay, scroll lock, Escape-to-close and focus handling
- **Sticky mobile call bar** with Call and WhatsApp buttons
- **Photo gallery** with a keyboard-navigable lightbox (Esc, ← and →)
- **Embedded Google Map** and external map link
- **Infrastructure section** with an embedded YouTube video and a news source about the proposed Tadepalligudem airport pre-feasibility study
- **Buyer suitability cards** and a **due-diligence checklist**
- **Accessible FAQ accordion** (13 questions)
- **Enquiry form** with name, phone, preferred contact method and visit date/time
- **Disclosure block** stating that listing details are unverified

---

## SEO and Structured Data

- Title, meta description, robots, canonical URL and Open Graph tags
- JSON-LD `@graph` containing `WebPage`, `Residence`, `BreadcrumbList` and `FAQPage`
- Microdata breadcrumb in the visible markup
- Semantic sections with anchor IDs (`#about`, `#price`, `#photos`, `#location`, `#future-development`, `#faq`, `#contact`, `#enquiry`)

---

## Project Structure

```
.
├── index.html   # The whole site (HTML + CSS + JS)
└── README.md
```

Page sections in order: Header → Breadcrumb → Hero → About & Quick Facts → Price → Gallery → Location → Infrastructure → Suitability → Due Diligence → FAQ → Contact → Enquiry Form → Disclosure → Footer.

---

## Getting Started

### Run locally

Open the file directly in a browser, or serve it locally:

```bash
# Python
python3 -m http.server 8000

# or Node
npx serve .
```

Then visit `http://localhost:8000`.

### Deploy

Because it is a static file, it can be hosted anywhere: GitHub Pages, Netlify, Vercel, Cloudflare Pages, or any basic web host. Upload `index.html` and you are done.

---

## Customisation Guide

Search the file for the items below and update them as needed.

| What to change | Where |
|---|---|
| **Price** | Hero, Quick Facts table, Price box, FAQ, meta tags, JSON-LD, WhatsApp prefilled messages |
| **Phone number** | All `tel:` and `wa.me/` links, plus visible text in the contact sections and FAQ (the number is repeated many times, so use find-and-replace) |
| **Canonical / OG URL** | `<link rel="canonical">`, `og:url`, and JSON-LD `url` / `@id` values (currently `https://example.com/...` placeholders) |
| **Photos** | Five `<img>` tags in `#photos`, the `galleryImages` array in the script, the hero `background`, and `og:image` |
| **Map location** | Iframe `src` in `#location`, the "View on Google Maps" link, and `geo` in JSON-LD |
| **Colours** | CSS variables in `:root` (`--accent`, `--primary`, `--bg`, etc.) |
| **Last updated date** | Disclosure section and `datePublished` / `dateModified` in JSON-LD |
| **Video** | YouTube ID `1gYdqDss2_4` in the nav, embed, and footer links |

---

## Known Limitations and Suggested Improvements

These are worth addressing before treating the page as production-ready.

1. **The enquiry form does not send data anywhere.** `submitForm()` only shows a success message and resets the form. Connect it to a form service (Formspree, Netlify Forms, Google Apps Script, etc.) or a backend, otherwise enquiries are silently lost.
2. **Placeholder canonical URL.** `https://example.com/...` appears in the canonical tag, Open Graph URL and JSON-LD. Replace it with the real live URL.
3. **Externally hosted images.** All photos are loaded from `image.qwenlm.ai`. If those links expire or change, the gallery, hero and social preview image will break. Download the images and host them alongside the page.
4. **Same image used for hero and first gallery item**, so the "Front Elevation" photo is repeated.
5. **`rel="dofollow"` is not a valid value.** Links are followed by default; remove it, or use `rel="noopener noreferrer"` on `target="_blank"` links.
6. **Map precision vs. copy.** The page says the exact location is shared only during a visit, but the map embed and JSON-LD use specific coordinates. Reduce precision if privacy matters.
7. **Structured data type.** `Residence` describes the property but has no offer or price. Consider adding an `Offer` (or `RealEstateListing`) with price and currency so search engines can read the asking price.
8. **Breadcrumb links** point to external sites (Wikipedia, Incredible India) rather than pages on this site.
9. **Unverified listing data.** Property details, tax status and the airport-related information should be verified before publishing. The page already includes a disclosure, but verify the facts themselves.
10. **Personal contact details** (phone number) are public in the source. Avoid committing them to a public repository if that is a concern.

---

## Browser Support

Modern evergreen browsers (Chrome, Edge, Safari, Firefox). Glass effects use `backdrop-filter` with `-webkit-` fallbacks; in browsers without support the page still renders with translucent backgrounds.

---

## Credits and Sources

- Airport pre-feasibility news: *The Hindu* (linked in the Infrastructure section)
- Area information: Wikipedia – Tadepalligudem
- Map: Google Maps embed

---

## Disclaimer

Information on the page is provided by the property owner and has not been independently verified. Buyers should confirm title, approvals, measurements, taxes and all other details with the relevant authorities and professionals before purchase.
