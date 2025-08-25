# Prompt Log — ShopSmart Styling

> Keep this log of what you asked AI, what it suggested, what you implemented, and a short reflection.

---

## 1) Prompt
“How can I vertically and horizontally center a hero’s headline and button using pure CSS, without extra wrappers?”

**AI Response Summary**  
Suggested using `display: grid; place-items: center;` on the hero plus a min-height and padding; mentioned `flex` as an alternative.

**My Implementation**  
Used `display: grid; place-items: center; min-height: 58vh;` on `.hero` and kept content in a `.hero-content` for text alignment.

**Reflection**  
Grid centering is cleaner than juggling multiple flex properties. It also adapts well on mobile.

---

## 2) Prompt
“What’s a subtle, performant hover effect for primary buttons that doesn’t rely on heavy shadows?”

**AI Response Summary**  
Recommended a light translateY on hover with a short transition and slight brightness/contrast change on `:active` for click feedback.

**My Implementation**  
`transition: transform .15s ease;` with `button:hover { transform: translateY(-2px); }` and `button:active { filter: brightness(.95) }`.

**Reflection**  
Feels crisp and accessible; minimal motion keeps it snappy on low-end devices.

---

## 3) Prompt
“How do I make a 3-column product layout that collapses to 2 and then 1 column using CSS Grid?”

**AI Response Summary**  
Use a 12‑column grid and set cards to `grid-column: span 4;` then change spans via media queries.

**My Implementation**  
`.products { grid-template-columns: repeat(12, 1fr); }` and card spans `4/6/12` across breakpoints.

**Reflection**  
Span math is straightforward and more controllable than `auto-fit` for this use case.

---

## 4) Prompt
“Give me a clean dark theme palette with two brand accents that works on LCDs.”

**AI Response Summary**  
Offered a neutral dark background, muted text, and complementary blue/cyan accents. Suggested CSS variables for consistency.

**My Implementation**  
Defined `--bg`, `--panel`, `--muted`, `--text`, `--brand`, `--brand-2`, `--accent` in `:root` and reused across components.

**Reflection**  
Variables sped up iteration and made hover/focus states consistent.

---

## 5) Prompt
“What’s the simplest way to keep images uniform inside product cards?”

**AI Response Summary**  
Use `aspect-ratio` with `object-fit: cover` on the `img` element to avoid layout shifts.

**My Implementation**  
`.product-card img { aspect-ratio: 16/11; object-fit: cover; }`

**Reflection**  
No more jumping content as images load—much smoother UX.

---

## 6) Prompt
“How can I make the header appear frosted and stay visible while scrolling?”

**AI Response Summary**  
Use `position: sticky; top: 0;` with a semi‑transparent background and `backdrop-filter: blur(8px)` plus a subtle border.

**My Implementation**  
Added sticky header with gradient backdrop and a soft bottom border for separation.

**Reflection**  
Improves navigation without feeling heavy. Works well in Chromium; acceptable in browsers that ignore `backdrop-filter`.
