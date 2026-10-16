# Pacha Satta

An interactive chameleon garden. The page is a single self-contained HTML file: a sunlit canopy of branches, leaves, flowers and fruit, with a chameleon at the centre that watches the cursor, changes colour when you touch the garden, and catches worms with its tongue.


---

## 1. Idea

A miniature heaven inside a giant tree canopy. The viewer does not read a page; they visit a small living world and play with it.

The chameleon is the emotional centre. Its eyes follow the viewer, its body takes the colour of whatever the viewer touches, and the worms hidden in the fruit and branches give the viewer a small game to discover. The wind and the sound make the garden feel alive even when nothing is being touched.

**Art direction:** low-poly and origami-style faceted shapes, a bright botanical palette (emerald, lime, turquoise, coral, orange, yellow, magenta, violet, sky blue), and a warm sky-and-valley backdrop with waterfalls.

---

## 2. Project details

| Item | Detail |
| --- | --- |
| Name | Pacha Satta |
| Type | Single-page interactive illustration / web experience |
| Delivery | One HTML file (HTML, CSS, JavaScript, inline SVG). No build step, no server |
| Target | Desktop browsers first; phones and tablets supported by design (touch input) |
| Sound | Generated in the browser (Web Audio). No audio files |
| Fonts | Cinzel Decorative (Google Fonts), with Georgia as fallback |
| Owner | Divakar S and Sashi Pillai M |

### Features

- **Garden scene:** sky, clouds, distant mountains, waterfalls, a valley, and a canopy of layered branches, twigs, leaves, flowers and fruit. Layout is generated from a fixed seed, so the garden looks the same on every visit.
- **Cursor-tracking eyes:** two eyes that follow the pointer with a soft spring. When the pointer is still, they wander gently.
- **Colour by touch:**
  - tap the chameleon's body: a new vibrant colour, never the same one twice in a row
  - tap a branch, leaf, flower or fruit: the chameleon takes that object's colour
  - colour eases in smoothly rather than snapping
- **Wind:** a slow left-to-right, right-to-left breeze over a 20-second cycle, with gusts. Leaves and flowers sway by different amounts. Branches stay still.
- **Worms:** natural segmented worms poke out of the larger fruit and lie along the branches. They wiggle and creep slowly.
- **Tongue game:**
  1. Tap the chameleon's **nose**: the tongue shows for 1.5 seconds.
  2. Double-tap the **tongue** while it is out: the tongue now follows your pointer (or finger) across the whole garden.
  3. Touch a worm with the tongue tip: the worm sticks, the tongue pulls it back, and the chameleon chews.
  4. Double-tap the tongue again, or leave it still for 4 seconds, to put it away.
- **Respawn:** eaten worms return after 22 to 40 seconds.
- **Sound:** airflow that pans left and right, leaf rustles, branch creaks, a soft bite and chew for fruit, a tongue flick, a wet catch and a munch. Sound starts on the first tap (browsers require this), and a button in the top-right corner mutes it.
- **Title:** PACHA SATTA appears centred for five seconds and then settles at the top of the sky.

### Controls

| Action | Mouse / trackpad | Touch |
| --- | --- | --- |
| Change chameleon colour | Click body | Tap body |
| Change colour from the garden | Click branch, leaf, flower or fruit | Tap the same |
| Show tongue | Click nose | Tap nose |
| Operate tongue | Double-click tongue, then move | Double-tap tongue, then drag |
| Replay title | Top-left button | Top-left button |
| Mute / unmute | Top-right button | Top-right button |

---

## 3. Factors

Factors that shape the design, what they affect, and how they are handled.

| Factor | Why it matters | How it is handled |
| --- | --- | --- |
| Browser autoplay rules | Audio cannot start on page load | Audio starts on the first tap, with a mute button |
| Performance | Hundreds of leaves are animated every frame | Layout is built once; only transforms change per frame; no filters or blur |
| Touch input | Hover-only controls would fail on phones | All actions use tap, double-tap and drag |
| Overlapping objects | Leaves and fruit can cover branches and the tongue | Foreground foliage is decorative only, and the tongue layer sits above the chameleon |
| Modern CSS | Two-tone chameleon patches use `color-mix` | Supported in current Chrome, Edge, Safari and Firefox; older browsers show plain green |
| External font | Title font loads from Google Fonts | Georgia fallback keeps the title readable |
| Reduced motion | Some visitors ask for less movement | Wind is reduced to 30 percent; body bob and chew animations are turned off |
| Garden size | The canopy is large, but the screen is small | Scene scales to fit; the chameleon stays at bottom centre on any screen shape |
| Privacy | No data is collected | No accounts, cookies, analytics or network requests beyond the font |

---

## 4. Summary

Pacha Satta is a single-file, browser-based garden in which a chameleon watches the viewer, takes on the colours of what it touches, and hunts worms with its tongue. The core experience is implemented: the scene, eye tracking, colour changes, wind, sound, the nose-to-tongue sequence, double-tap control, worm catching and respawn.

Still to do before a public release: falling leaves, pixel-based colour sampling, a closer match to the reference artwork, full testing on phones and other browsers, keyboard access for the tongue game, and the final title behaviour. See `task.md` for the full list, `SRS.md` for the requirements, and `assets list.md` for every asset and dependency.
