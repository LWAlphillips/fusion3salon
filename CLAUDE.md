# Fusion 3 Salon website — notes for Claude

Static Astro site for fusion3salon.com, deployed on Vercel from the `main` branch. Every push to `main` goes live in about a minute. Requests usually come from the salon manager, who isn't technical, so keep explanations plain.

## How to make changes
- Everyday content (hours, contact info, booking/gift card URLs, featured promos, announcement bar, specials, vouchers, services, policies, careers) lives in `src/content/site.json`. Edit there first. Keep it valid JSON.
- Look and feel (colors, fonts, radius) lives in the CSS variables in `src/styles/theme.css`.
- Pages are in `src/pages/`, and the shared header/footer is in `src/layouts/Base.astro`.
- Run `npm install && npm run build` before committing. It must build with no errors.
- Commit with a clear message describing what changed, then push to `main`.

## Guardrails (the owner asked for these)
- The only location is 722 Main Street, Pleasanton. Livermore and Brentwood are closed, so never mention them.
- Don't link out to aveda.com or davines.com, and don't mention Aveda Pure Privilege.
- Keep WCAG 2.1 AA: text contrast ≥ 4.5:1, alt text on informative images, real headings in order, visible focus states, and no autoplaying motion.
- Never remove or change entries in `vercel.json` redirects. They preserve 20+ years of Google ranking. If a page URL changes, add a 301 redirect.
- Keep the `HairSalon` structured data in `Base.astro` in sync. It reads from site.json automatically, so just keep site.json accurate.
- Don't invent prices, policies, awards or promises. Prices are shown in the booking system, not on the site.
- Before deleting content or making a big redesign, confirm with the requester.
