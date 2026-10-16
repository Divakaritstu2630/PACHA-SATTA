# Pacha Satta: Assets List

**Last updated:** 2026-10-16

This list covers every asset the page uses: the code file, the drawn artwork, the colours, the sounds, the fonts, the icons and the external dependencies. The page ships as one file and has no image or audio files.

---

## 1. Deliverable files

| File | Type | Size (approx.) | Purpose | Notes |
| --- | --- | --- | --- | --- |
| `index.html` | HTML, CSS, JavaScript, inline SVG | 32 KB | The whole experience | Open directly in a browser |
| `README.md` | Markdown | — | Project overview, details, factors, summary | Documentation |
| `SRS.md` | Markdown | — | Software requirements specification | Documentation |
| `task.md` | Markdown | — | Task list and status | Documentation |
| `assets list.md` | Markdown | — | This file | Documentation |

---

## 2. Drawn artwork (SVG, created in code)

No raster images are used. Every shape is drawn in SVG at a design size of 1600 × 900 and scaled to fit the screen.

### 2.1 Scenery

| Asset | Description | Count | Layer |
| --- | --- | --- | --- |
| Sky | Vertical gradient, blue to pale | 1 | Back |
| Clouds | Soft white ellipses with pale undersides | 5 | Back |
| Distant mountains | Two faceted ridges, teal and green | 2 layers | Back |
| Plateau | Small green rise with tree tops | 1 | Back |
| Waterfalls | White tapering streaks with mist | 3 | Back |
| Valley | Green ground with scattered tree blobs | 1 base + 150 blobs | Back |

### 2.2 Foliage

| Asset | Description | Count | Layer |
| --- | --- | --- | --- |
| Back leaves | Dark greens, static, depth only | ~200 | Back canopy |
| Branch leaves | Faceted two-tone leaves with a midrib line | Several hundred | Middle |
| Foreground leaves | Large edge leaves, decorative, never interactive | ~14 | Front |
| Flowers | Five-petal faceted flowers with yellow centres | 56 | Middle |
| Foreground flowers | Two large violet flowers at bottom corners | 2 | Front |

### 2.3 Branches and fruit

| Asset | Description | Count | Layer |
| --- | --- | --- | --- |
| Main branches | Curved, bark-coloured, with a light highlight line | 6 | Branches |
| Secondary branches | Thinner branches off the main ones | ~18 | Branches |
| Twigs | Thin shoots off the secondary branches | ~36 | Branches |
| Perch branch | Thick branch under the chameleon | 1 | Branches |
| Large fruit | Single faceted fruit with highlight and shadow | 7 | Fruit |
| Grape-like clusters | Round faceted fruit in small groups | 3 clusters (21 fruit) | Fruit |

### 2.4 Worms

| Asset | Description | Count | Home |
| --- | --- | --- | --- |
| Fruit worms | Segmented body, half-emerged from fruit | ~6 | Fruit |
| Branch worms | Segmented body lying on top of a branch | 14 | Branches |

Each worm is made of 7 or 8 circles, with a dark head marker and an invisible hit area.

### 2.5 Chameleon

| Part | Description |
| --- | --- |
| Body | Faceted polygons: torso, head, casque, two legs, hind leg, tail |
| Facet shading | Dark and light overlays on the body |
| Two-tone patches | Three patch shapes (orange, cyan and magenta mixes) |
| Eyes | Two eyes: a large front eye and a smaller one behind it. Each has a moving pupil and a glint |
| Mouth | Single dark line |
| Nose zone | Invisible circle that starts the tongue flick |
| Tongue | Pink stroke with a rounded tip and a small shine |

### 2.6 Interface icons

| Icon | Where | Description |
| --- | --- | --- |
| Sprout | Above the title | Two gold-and-green leaves on a stem |
| Leaf | Top-left button | Single leaf with a stem |
| Speaker | Top-right button | Speaker with two sound waves |
| Mute | Top-right button | Speaker with a cross, shown when muted |
| Decorative dots | Right edge | Four small dots, first one bright |

---

## 3. Colour palette

### 3.1 Scene colours

| Use | Hex values |
| --- | --- |
| Sky | `#3aa6e4`, `#9ddcf5`, `#eafbff` |
| Mountains | `#6fb8ab`, `#8fd0c2`, `#4f9b8c`, `#3d8e7b` |
| Valley | `#2d7f5e`, `#1e5e48`, `#4caf6a`, `#7cc96b`, `#2e8b57`, `#8fd17a`, `#5fb37a` |
| Page background | `#0c3a30` |

### 3.2 Foliage and branch colours

| Use | Hex values |
| --- | --- |
| Bark | `#7a4f2c`, `#8b5a33`, `#6b4226`, `#94643a`, `#7d4a2e` |
| Bark highlight | `#c79a64` |
| Leaves | `#1f9d55`, `#2fb16a`, `#84cc16`, `#4d7c0f`, `#14b8a6`, `#3f7d3a`, `#9acd32`, `#0f766e`, `#22a06b` |
| Back leaves | `#0e5a3e`, `#136b45`, `#2b6b1e`, `#0b4d48`, `#1d5e2c` |
| Stems | `#5b3a1c`, `#5fb84a` |

### 3.3 Object colours (used when the chameleon takes a colour)

| Object | Hex values |
| --- | --- |
| Chameleon body (tap on body) | `#2ecc8f`, `#a3e635`, `#22d3ee`, `#ff7a59`, `#ffa726`, `#facc15`, `#e040fb`, `#8b5cf6`, `#38bdf8` |
| Flowers | `#f472b6`, `#d946ef`, `#8b5cf6`, `#fb923c`, `#fb7185`, `#38bdf8`, `#fde047` |
| Fruit | `#e11d48`, `#fb923c`, `#facc15`, `#ff9f1c`, `#ff8c1a`, `#7e22ce`, `#c3e88d` |
| Worms | `#c97a6c`, `#b5654f`, `#d98e80`, `#a86a4e`, `#c98a5e` |

### 3.4 Interface colours

| Use | Hex value |
| --- | --- |
| Title text (cream) | `#fff4d6` |
| Title shadow | `#3b2310` |
| Button ring (gold) | `#e9c978` |
| Button fill | `rgba(14, 58, 46, 0.82)` |
| Dots | `rgba(255, 246, 220, 0.5)` |

---

## 4. Sound

No audio files are used. Every sound is generated in code with the Web Audio API.

| Sound | How it is made | Used when |
| --- | --- | --- |
| Airflow | Looping white noise, band-passed, panned left and right over 20 seconds, with a slow gust | Continuous while unmuted |
| Rustle | Short band-passed noise bursts, high frequency | Tapping a leaf or flower, ambient |
| Branch creak | Falling sawtooth tone through a low-pass filter | Tapping a branch, occasional ambient |
| Fruit bite | Low-pass noise burst plus a short falling tone | Tapping a fruit |
| Chewing | Three short band-passed bursts | After a bite and after eating a worm |
| Tongue flick | Rising sine tone | Nose tap; control mode starts |
| Catch | Short falling sine tone | Worm caught by the tongue |
| Munch | Low-pass and band-passed bursts | Worm eaten |

Master volume: 0.8. Mute sets it to 0.

---

## 5. Fonts

| Font | Use | Source | Fallback |
| --- | --- | --- | --- |
| Cinzel Decorative (bold) | Title PACHA SATTA | Google Fonts | Cinzel, Georgia, Times New Roman, serif |

Font licence: SIL Open Font Licence (Google Fonts). Free for this use.

---

## 6. External dependencies

| Dependency | Purpose | Required? | If unavailable |
| --- | --- | --- | --- |
| `fonts.googleapis.com` | Stylesheet for Cinzel Decorative | No | Title uses Georgia |
| `fonts.gstatic.com` | Font files | No | Title uses Georgia |
| Web Audio API (browser) | All sound | No | Page is silent |
| `color-mix()` (browser CSS) | Two-tone chameleon patches | No | Chameleon is a single colour |
| Pointer events (browser) | All input | Yes | Page cannot be used |

There are no JavaScript libraries, frameworks, CDN scripts or build tools.

---

## 7. Reference material (not shipped)

| Item | Location | Use |
| --- | --- | --- |
| Reference artwork (garden with chameleon, origami and crayon style) | `/root/.claude/uploads/3122aa32-e4b2-5c88-ae36-aea170e9d12d/79f51a4e-image.jpg` | Visual target for layout and colour. Not included in the page; see task list Stage 6 for the decision on using it as a backdrop |
| Project brief (text) | Supplied in the conversation | Source of the interaction and sound requirements |

---

## 8. Assets still to create

| Asset | Needed for | Stage |
| --- | --- | --- |
| Falling leaf shape (small faceted leaf, two sizes) | Falling leaves | 2 |
| Petal shape (separate from flower head) | Petal drift | 2 |
| Chameleon head and eye refinement | Visual match | 6 |
| Extra distant details (birds, blossoms) | Visual match | 6 |
| Optional: reference image as backdrop (if chosen) | Visual match | 6 |
| Optional: sampled colour map (if built) | Colour from artwork | 7 |

---

## 9. Asset checklist before release

- [ ] Every shape renders with no missing fill or stroke
- [ ] No text is clipped at any screen size
- [ ] Colours checked on a bright phone screen and a dim laptop screen
- [ ] Font fallback checked with the font blocked
- [ ] Sound checked with headphones and speakers
- [ ] Documentation files match the build (version number, feature status)
