NEXTGEN WORKFORCE — WEBSITE V1.2

Added in V1.2:
- Two clear user paths: businesses needing staff and candidates looking for work.
- Verified proof section based on supplied brandboard: 120+ placements, 30+ active partners, 15+ support availability.
- Why NextGen / foundation section using the client's Trust, Efficiency, Structure, Quality Talent and Growth framework.
- Process section redesigned without the accidental Drive-folder screenshot.
- Corporate address added to footer.
- English remains the default for first-time visitors; ES control switches to Spanish.
- No AI-generated replacement imagery used.
- Basic candidate form UI remains intentionally unconnected until final recipient/backend is confirmed.

V2 additions:
- Candidate city autocomplete UX (local Utah suggestion set, ready for live Places API later).
- Searchable multi-select work-experience roles using categories confirmed on NextGen's current website.
- Structured availability builder: days, quick availability type, time range, custom notes.
- English level selector restored from NextGen's current application flow.
- Dedicated "Build up your team" company form matching the current site's required structure:
  company email, first name, last name, staff service, company name, phone number.
- Homepage business CTA now routes to the dedicated employer form.

V2.1:
- All candidate Apply CTAs now go directly to apply.html.
- All employer staffing CTAs now go directly to work-with-us.html.
- Employer form rebuilt with actual staffing-request details: industry, roles, worker count, timing, employment type, work location, detailed needs and final notes.

V2.3:
- Added the official client-supplied NextGen 3D logo animation as a brief branded intro.
- Intro appears once per browser tab/session on the homepage only.
- The website loads underneath it; the animation is decorative rather than a real loading screen.
- Official ~5.1 s video plays at 3x speed and is capped at ~1.9 s.
- Intro is skipped automatically for users with reduced-motion enabled.

V2.4: Brand intro shortened to roughly 1.4 seconds (3.7x playback, 1.5 s hard cap).

V2.5: Decorative brand intro shortened to 0.8 seconds (6.5x playback, 800 ms hard cap).

V2.6:
- Decorative intro shortened to 0.5 seconds.
- Mobile pass: tighter spacing, larger touch targets, stacked CTAs, cleaner hero proportions,
  one-column service/proof layouts, improved forms, better mobile typography and overflow handling.

V2.7:
- Fixed inconsistent logo intro playback on slower/mobile connections.
- The 0.5-second intro timer now starts on the video's real `playing` event.
- sessionStorage is only marked after playback actually begins.
- Added a 4-second safety fallback if media cannot start.

V2.9:
- Hero CTA copy remains “I'm looking for a job”.
- Replaced the static white-background 3D logo card with the official rotating logo video.
- Hero logo loops perpetually at the official animation's original speed.
- Black video background is visually blended into the dark hero using CSS screen blending.
- Loader behavior remains unchanged.


V3.1 — LIVE GOOGLE REVIEWS
--------------------------
The homepage now has a Google Reviews section connected through a Cloudflare Pages Function.

How it updates:
- Browser requests /api/google-reviews.
- Cloudflare fetches current rating/reviews from Google Places.
- Cloudflare caches the result for 6 hours to control API usage/cost.
- After the cache expires, a later visitor causes a fresh Google fetch.
- No review text is hard-coded, so new/changed reviews can appear automatically when Google returns them.

ONE-TIME CLOUDFLARE SETUP REQUIRED:
1. In Google Cloud, enable:
   - Places API (New)
2. Create an API key and restrict it appropriately.
3. In Cloudflare Pages > NextGen project > Settings > Environment variables, add:
   GOOGLE_PLACES_API_KEY = your Google key
4. Optional but recommended:
   GOOGLE_PLACE_ID = the exact Google Place ID for NextGen Workforce
   OR
   GOOGLE_PLACE_QUERY = a query that uniquely finds the listing, e.g. "NextGen Workforce 435-494-2395"
5. Redeploy after adding variables.

Important:
- Google Places may return a selected subset of reviews rather than every review on the profile.
- The UI preserves reviewer author attribution and links back to Google.
- For full owner-level access to all Business Profile reviews, Google Business Profile API + OAuth is a different, more complex integration.

V3.2:
- Google Reviews display now prioritizes the strongest useful reviews returned by Google.
- Ranking order: higher star rating, meaningful written detail, then newer publish time.
- Shows up to 6 reviews when the API returns that many.
- Review text, rating, author and links are never rewritten or fabricated.

V3.4:
- Removed the FOH + BOH explanatory block from the public homepage.
- Removed the technical Google cache/update note from the public reviews UI.
- Google Reviews section is now invisible until valid live Google data loads.
- If Google Places is not configured or temporarily fails, the reviews section disappears silently instead of showing an error to visitors.
- Google Reviews backend/function is preserved so it can be configured next without rebuilding the page.

V3.5:
- Restored the Google Reviews section so it is always part of the page.
- If the live Google connection is not configured yet, the section stays visible with a clean non-technical placeholder.
- Once Google Places is configured, the placeholder is automatically replaced by live review cards.

V3.6:
- Removed the Google Places API / Cloudflare Reviews dependency.
- Added the 4 verified 5-star Google reviews supplied by the client/user as static website content.
- Uses text + reviewer name only; no reviewer photos/screenshots.
- Review wording is preserved from the supplied Google Maps screenshots and is not rewritten.
- No Google billing/API key is required for this version.

V3.7: Removed the visible total review count. The summary now says only “Google reviews” while retaining the 5.0 rating.

V3.8 FINAL POLISH:
- Added restrained scroll-reveal motion with staggered timing.
- Added subtle hover lift and pointer-following highlights to cards on desktop.
- Added button press/hover microinteractions.
- Added gentle depth/parallax to hero/decorative media.
- Added a minimal scroll-progress accent to the staffing solutions area when the layout exposes a compatible grid.
- Added reduced-motion accessibility support.
- Preserved all V3.7 content, static Google reviews, forms, and existing structure.

V3.9:
- Fixed only the items previously marked ❌.
- Candidate role search no longer uses the old FOH/Culinary-BOH/Hospitality/LuxClean architecture.
- Employer role search uses the same new 8-category staffing structure and detailed positions.
- Employer static service selector updated to the 8 current categories where applicable.
- Main Our Staffing Solutions category headings now participate in EN/ES language switching.

V3.10:
- Google Reviews are now shown in English.
- The supplied screenshots did not expose the exact original English wording for every review, so the site uses faithful English translations of the verified text provided.
- Reviews now rotate automatically in a carousel.
- Desktop shows 2 at a time; mobile shows 1 at a time.
- Added previous/next controls, dots, swipe support, pause-on-hover/focus, and reduced-motion support.
- Kept the 5.0 summary and changed the label to “Google Reviews” without exposing the total review count.
