# Editing the Fusion 3 Salon website

The site updates by itself about a minute after a change is saved to this repository (Vercel watches it). You don't need to log in to Vercel.

## The easy way: ask Claude

With GitHub connected to Claude, just describe the change. For example:

- "On the Fusion 3 site, change Saturday hours to 9 AM – 5 PM."
- "Add a featured card for the new Aveda Botanical Repair launch, ending December 31."
- "Turn on the top announcement bar: 'Closed Thanksgiving Day.'"
- "Make the buttons a darker green."
- "Add 'Gloss Treatment' to the Color services with a one-line description."

## Where things live

| What you want to change | File |
|---|---|
| Hours, phone, address, booking and gift card links, featured promos, announcement bar, specials, vouchers, services, policies, careers | `src/content/site.json` |
| Colors, fonts, button shape | `src/styles/theme.css` |
| Images (add new ones here, then reference them as `/images/your-file.jpg`) | `public/images/` |
| Page layouts and wording outside the content file | `src/pages/` |
| Old-URL redirects (protects Google rankings — don't remove these) | `vercel.json` |

## Rules of thumb

- **Featured cards** (`featured` in site.json) can have an `ends` date (`YYYY-MM-DD`). They hide automatically after that date.
- **Announcement bar**: set `"show": true` or `false`.
- **Booking link** (`bookingUrl`) is used by every "Book" button. Change it in one place only.
- Keep text colors dark on light backgrounds so the site stays accessible (WCAG 2.1 AA).
- Every image needs a short `imageAlt` description (what the image shows) for screen-reader users.
- Don't delete or rename existing page URLs without adding a redirect in `vercel.json`.

If a change ever breaks something, GitHub keeps every previous version. Ask Claude to "revert the last change to the Fusion 3 site."
