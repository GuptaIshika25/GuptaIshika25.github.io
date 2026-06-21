# Ishika Gupta — Portfolio Design Spec

The single source of truth for the look and feel. Built to be handed to Claude Code (turn on the Frontend Design skill) or built here.

## North star

**Quiet canvas, loud craft.** A calm, warm, artistic, minimal page, with one or two pieces of exquisite micro-interaction on top. Restraint everywhere, delight in the details. This is the opposite of a loud, glowy, techy site. The personality comes from craft and restraint, not from effects.

Reference map (what inspired what):
- Adrian Hiotis — the warm off-white background, the calm artistic feel (her favorite).
- Jenny Atkins — clean, refined typography.
- Nicolas Backal — sections that pop in as you scroll, strong text-and-image balance (but warmer, his white was too harsh).
- Samuel Faith — projects that cascade in one after another.
- Ben Sol — soft wavy/organic transition between sections.
- Aucadian — the custom circular cursor and the project hover (zoom + shade + circle cursor); her overall favorite.

## Palette (warm, light-default)

- Background (warm bone): `#F3EFE7`
- Surface / cards (slightly lifted): `#FAF7F1`
- Alt section band (for separation): `#EDE8DD`
- Text primary (warm near-black): `#1C1B17`
- Text muted (warm gray): `#6E695E`
- Quiet accent (charcoal, does the UI work): `#2B2A25`
- Sand / taupe (secondary warm neutral, dividers + fills): `#CDC3B0`
- Hairline / border: `rgba(28,27,23,.12)`
- Spartan green (RARE jewel accent only): `#18453B`

Rule on green: it appears only in tiny moments. A single small dot, one hover detail, the inner dot of the cursor, a link underline on hover. Never a section background, never a big button fill. The page reads warm and neutral; green is a quiet signature, not the theme.

Optional warm dark mode (secondary, not the default): bg `#1A1916`, text `#F3EFE7`, muted `#9A9486`. Same green rule. Only build this after the light version is done.

## Typography

Small, refined, clean. She explicitly likes small fonts. No giant shouty display headlines.

- Primary typeface: a warm, refined grotesque. Recommended **Hanken Grotesk** (Google Fonts). Alternative: Inter Tight.
- Optional artistic accent: **Fraunces** italic (Google Fonts), used sparingly and small for labels or a single pull-quote, to add an editorial, artistic touch.
- Sizes (keep them restrained):
  - Body: 15px, line-height 1.7
  - Small labels / meta: 12–13px, letter-spacing slightly open
  - Section headings: 22–30px (NOT 48px+), weight 500
  - Hero name: the one allowed larger moment, ~40px max, still elegant not huge
- Generous whitespace is the main design material. Let things breathe.

## Layout and section order

Reordered per her note: introduce herself first.

1. **Intro / hero** — short, artistic introduction. Name, one refined line on who she is, a calm one or two sentences. The podcast player lives here, styled quietly. Optional small photo.
2. **Selected work** — the flagship AI Newsroom, presented with the signature hover interaction.
3. **Case studies** — WalletHub, StockPulse, the consulting reflection, as an editorial list or restrained cards, each with the hover treatment.
4. **Skills** — the two downloadable Claude skills.
5. **Reading** — 5 to 7 picks.
6. **About + photos** — the fuller story and the photo film-strip.
7. **Contact / footer** — two emails, LinkedIn, GitHub.

Sections separate through generous space and a subtle change of layout, plus a soft wavy/organic divider (Ben Sol) between a couple of them. You should always feel where one ends.

## Photos

Not a 2x2 grid. A horizontal film-strip the user drags or scrolls through. Warm framing, consistent aspect ratio, calm.

## Motion and interaction (the craft)

All eased and gentle. Nothing snappy or flashy.

1. **Custom cursor (signature).** A small ring follows the mouse. Default: a thin charcoal ring, ~12px. On hover over any interactive element it grows into a filled circle (~40px) with a tiny Spartan-green dot or a small "View" label inside. Smooth lerp/easing so it trails slightly. MUST disable on touch devices and fall back to the normal cursor; respect `prefers-reduced-motion`.
2. **Project / work hover (from her screenshots).** On hover over a work image: image scales up ~1.04, a translucent dark overlay (`rgba(20,19,16,.45)`) fades in over it, and the custom cursor becomes the filled circle. Title can fade up. Reverse smoothly on mouse-out.
3. **Scroll reveals (Nicolas).** Sections and elements fade and rise in as they enter the viewport. Subtle, ~20px travel, eased.
4. **Staggered project reveal (Samuel).** When the work section enters view, items animate in one after another with a small delay between each, not all at once.
5. **Wavy divider (Ben Sol).** A soft organic SVG wave or curved transition between two key sections.
6. Hover micro-states everywhere: links get a quiet underline grow, cards lift a few px, all eased.

## Accessibility and robustness

- Respect `prefers-reduced-motion`: disable scroll animation, cursor trailing, and hover zoom; show everything static.
- Custom cursor only on devices with a fine pointer (`@media (pointer:fine)`); never on touch.
- Keep small fonts above a readability floor (body not below 15px; never below 13px for meaningful text).
- High enough contrast on the warm palette (text `#1C1B17` on `#F3EFE7` passes).

## Build notes

- One self-contained `index.html`, vanilla JS, no framework. Hostable on GitHub Pages as-is.
- Reuse the real content already written: the three case study cards, the flagship copy, the footer links.
- Podcast player: plays `audio/latest.mp3`, reads `audio/episode.json` for the label, fails gracefully. (Daily MP3 is pushed by the AI Newsroom workflow.)
- Turn on the Frontend Design skill in Claude Code to avoid generic output.
- Deploy: GitHub Pages, free subdomain first, custom domain later.
