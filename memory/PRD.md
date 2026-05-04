# Birthday Hub PRD

## Original problem statement
A static "It's my birthday 🎂" HTML page (Birthday Hub) shared by the user with several fixes requested.

## Requested fixes (Jan 2026)
1. Remove all hardcoded "isha" text
2. Ask user name on entry, display everywhere
3. Save gifts using localStorage
4. Show all gifts in a public wall section
5. Don't break the existing layout
6. Remove "Build your own cup…" subtitle under Buy Me Coffee
7. "Stuck on what to gift me" (was "her")
8. "Drop a sweet little note for me 💌" on Message Wall

## Architecture
- Single static HTML page served from `/app/frontend/public/index.html`
- React (CRA) is intentionally inert — `App.js` returns null; `#root` is hidden via CSS
- All persistence via `localStorage` keys: bdayUser, bdayMessages, bdayCoffees, bdayBouquets, bdayWishes
- No backend usage; FastAPI server kept as default placeholder

## Implemented (May 2026 session)
- Static birthday hub with: landing → name modal → app
- Sections: Home (spin wheel), Buy Me Coffee, Wishlist Roulette, Message Wall, Bouquet maker, Gift Wall
- Coffee builder with animated layered mug, dynamic drink name, receipt
- Bouquet selector with wrapped-bouquet illustration and traits message
- Gift Wall with 3 tabs (Coffees, Bouquets, Wishlist), counts, refresh, clear
- Confetti, ambient floaters, toast, name modal with empty-submit guard
- All visitor-facing copy uses dynamic username; no "isha" anywhere
- All interactive elements tagged with `data-testid`

## Backlog / Future
- P2: Optional FastAPI + MongoDB persistence so Gift Wall is truly cross-device "public"
- P2: Share button (copy link / WhatsApp share) for the gift wall
- P2: Sound effects on confetti / brew / wrap
