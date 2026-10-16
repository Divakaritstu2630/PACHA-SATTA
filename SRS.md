# Software Requirements Specification: Pacha Satta

**Version:** 1.0 (interactive build)
**Date:** 2026-10-16
**Owner:** Sashi Pillai M
**Status:** Draft for review. Requirements marked *Implemented* are in `index.html`; those marked *Pending* are not.

---

## 1. Introduction

### 1.1 Purpose

This document specifies the requirements for Pacha Satta, a single-page interactive illustration in which the user explores a botanical canopy and interacts with a chameleon.

### 1.2 Scope

Pacha Satta is delivered as one HTML file that runs in a modern browser with no server or build step. It contains:

- an animated SVG garden of branches, leaves, flowers, fruit and worms
- a chameleon with cursor-tracking eyes, touch-driven colour, and a tongue controlled by the user
- procedural environmental sound
- a title overlay

Out of scope for version 1: user accounts, saving progress, scores, multiplayer, server-side features, and analytics.

### 1.3 Definitions

| Term | Meaning |
| --- | --- |
| Canopy | The layered foliage and branches that frame the scene |
| Perch | The thick branch the chameleon sits on, at bottom centre |
| Nose zone | The small invisible target on the chameleon's snout that starts a tongue flick |
| Tongue exposure | The 1.5-second period in which the tongue is visible after a nose tap |
| Control mode | The state entered by double-tapping the tongue during exposure, in which the tongue follows the pointer |
| Catch | A worm is stuck to the tongue tip, pulled back, and eaten |
| Respawn | A worm returns to its home after being eaten |
| Pointer | Mouse, trackpad, pen or touch input |

### 1.4 References

- Project brief: "Pacha Satta, an interactive chameleon ecosystem" (supplied by the user)
- Reference artwork supplied by the user (origami, crayon-colour, Rapunzel and Jungle Book themes)

---

## 2. Overall description

### 2.1 Product perspective

A standalone experience. It is a single web page, can be opened from disk, and can be hosted as a static page or published as a link.

### 2.2 User classes

| Class | Description | Needs |
| --- | --- | --- |
| Visitor | Anyone who opens the page | Immediate, playful, beautiful experience with no instructions |
| Child or family viewer | Plays on a tablet or phone | Large targets, gentle motion, no text to read |
| Reviewer (the owner) | Checks the build | Clear feature set, easy to run and share |

### 2.3 Operating environment

- Current versions of Chrome, Edge, Safari and Firefox on desktop, tablet and phone
- Pointer events supported (mouse, touch and pen)
- Web Audio API for sound (optional: the page works silently without it)
- Google Fonts reachable for the title font (optional: falls back to Georgia)

### 2.4 Design and implementation constraints

- Plain HTML, CSS and JavaScript with inline SVG. No React, no game engine, no runtime dependencies.
- Single file deliverable, plus this documentation.
- No image files: all artwork is drawn in SVG; all sound is generated in code.
- Must not create a conventional landing page, dashboard, or on-screen tutorial.

### 2.5 Assumptions and dependencies

- The browser allows audio to start after a user gesture.
- The browser supports `color-mix()` for the chameleon's two-tone patches. Without it, the chameleon is a single colour.
- The garden is drawn at a fixed design size (1600 × 900) and scaled to fit the screen.

---

## 3. Functional requirements

Priority: **M** = must, **S** = should, **C** = could.

### 3.1 Scene and layout

| ID | Requirement | Priority | Status |
| --- | --- | --- | --- |
| FR-01 | The scene fills the full viewport with no visible empty margins | M | Implemented |
| FR-02 | The scene shows a sky, distant mountains, waterfalls and a valley beneath the canopy | M | Implemented |
| FR-03 | The canopy frames the edges and top of the screen, leaving a clear window of sky in the centre | M | Implemented |
| FR-04 | Branches cross the screen at varied angles, with secondary branches and twigs | M | Implemented |
| FR-05 | Leaves vary in size, orientation and shade, and are placed without a visible grid | M | Implemented |
| FR-06 | Flowers are scattered along branches in several colours | M | Implemented |
| FR-07 | Fruit hangs from branches, including larger fruit and grape-like clusters | M | Implemented |
| FR-08 | Foreground foliage at the edges is decorative and never blocks interaction with the chameleon, tongue or worms | M | Implemented |
| FR-09 | The layout is stable across page reloads (same seed) | S | Implemented |

### 3.2 Chameleon

| ID | Requirement | Priority | Status |
| --- | --- | --- | --- |
| FR-10 | The chameleon is at bottom centre, sitting on the perch branch | M | Implemented |
| FR-11 | The chameleon's body does not move toward the cursor; only the eyes do | M | Implemented |
| FR-12 | Each eye's pupil tracks the pointer and stays within the eye outline | M | Implemented |
| FR-13 | Pupil movement is eased, not instant | M | Implemented |
| FR-14 | When the pointer is still for 2.5 seconds, the eyes wander gently | S | Implemented |
| FR-15 | While the tongue is out, the eyes look toward the tongue tip | S | Implemented |
| FR-16 | The chameleon has a clear silhouette, a curled tail, four legs, a textured two-tone body and a clear head | M | Implemented (approximate to reference) |

### 3.3 Colour

| ID | Requirement | Priority | Status |
| --- | --- | --- | --- |
| FR-17 | Tapping the chameleon's body changes its colour to a new vibrant colour; the same colour is never chosen twice in a row | M | Implemented |
| FR-18 | Tapping a branch sets the chameleon to a bark or ochre colour | M | Implemented |
| FR-19 | Tapping a leaf sets the chameleon to a green (emerald, lime, olive or teal) | M | Implemented |
| FR-20 | Tapping a fruit sets the chameleon to that fruit's colour | M | Implemented |
| FR-21 | Tapping a flower sets the chameleon to that flower's colour | M | Implemented |
| FR-22 | Colour changes ease over time, not instantly | M | Implemented |
| FR-23 | Colour changes keep the chameleon's shading and facets | M | Implemented |
| FR-24 | Colour is taken from the touched object's palette, not from a sample of the screen | S | Implemented (palette only) |
| FR-25 | Colour is sampled from the rendered artwork, with the palette as fallback | C | Pending |

### 3.4 Environment

| ID | Requirement | Priority | Status |
| --- | --- | --- | --- |
| FR-26 | Wind alternates left-to-right and right-to-left over a smooth cycle, with gusts | M | Implemented |
| FR-27 | Small leaves and flowers react to wind more than large branches | M | Implemented |
| FR-28 | Branches do not move in the wind | M | Implemented |
| FR-29 | Leaves and flowers can be knocked by a tap and settle back | S | Implemented |
| FR-30 | Leaves occasionally detach and drift down with varied size, speed, rotation and sway | M | Pending |
| FR-31 | Falling leaves are intermittent and do not overwhelm the chameleon | M | Pending |
| FR-32 | Falling leaves are removed once they leave the screen | M | Pending |

### 3.5 Worms and tongue

| ID | Requirement | Priority | Status |
| --- | --- | --- | --- |
| FR-33 | Natural segmented worms appear on some fruit and on branches | M | Implemented |
| FR-34 | Worms wiggle and creep slowly | M | Implemented |
| FR-35 | Tapping the chameleon's nose shows the tongue for 1.5 seconds | M | Implemented |
| FR-36 | After 1.5 seconds without a double-tap, the tongue retracts into the mouth | M | Implemented |
| FR-37 | Double-tapping the tongue while it is visible enters control mode | M | Implemented |
| FR-38 | In control mode, the tongue tip follows the pointer across the whole screen | M | Implemented |
| FR-39 | The tongue tip sticks to a worm it touches and pulls it back to the mouth | M | Implemented |
| FR-40 | Eating a worm plays a chewing animation and a sound | M | Implemented |
| FR-41 | Control mode ends on a second double-tap, or after 4 seconds without pointer movement | M | Implemented |
| FR-42 | Eaten worms return after 22 to 40 seconds | S | Implemented |
| FR-43 | Worms are not caught by a plain tap; only the tongue catches them | M | Implemented |
| FR-44 | The state progression is: hidden → exposed → control → caught → retracting → eaten → ready again | M | Implemented |
| FR-45 | Tongue control can be used by keyboard | S | Pending |
| FR-46 | Worm discovery is triggered by a probability model on branch-click patterns (original brief) | C | Superseded: worms are now always present (see §6) |

### 3.6 Sound

| ID | Requirement | Priority | Status |
| --- | --- | --- | --- |
| FR-47 | All sound is generated in the browser; no audio files are downloaded | M | Implemented |
| FR-48 | Sound begins only after the first user gesture | M | Implemented |
| FR-49 | A visible button mutes and unmutes all sound | M | Implemented |
| FR-50 | Continuous airflow pans left and right with the wind | S | Implemented |
| FR-51 | Leaf rustles, branch creaks, fruit bites, chewing, tongue flicks, catches and munches play at the matching moments | S | Implemented |
| FR-52 | Occasional ambient rustles and creaks play while the page is open and unmuted | C | Implemented |

### 3.7 Title and interface

| ID | Requirement | Priority | Status |
| --- | --- | --- | --- |
| FR-53 | The title PACHA SATTA appears centred on load, with a small sprout icon above it | M | Implemented |
| FR-54 | After 5 seconds the title settles to the top of the sky and stays there | S | Implemented (open decision, see §6) |
| FR-55 | A button in the top-left replays the title animation | C | Implemented |
| FR-56 | No other buttons, menus, panels, tutorials or scores are shown | M | Implemented |
| FR-57 | The page can be re-opened and replayed without reloading | S | Implemented |

---

## 4. Non-functional requirements

### 4.1 Performance

| ID | Requirement | Target | Status |
| --- | --- | --- | --- |
| NFR-01 | Smooth animation on ordinary laptops and phones | About 60 frames per second | Not yet measured |
| NFR-02 | The page does not slow down over a long session | No growth in frame cost over 10 minutes | Not yet measured |
| NFR-03 | Animation uses transforms, not layout changes | Required | Implemented |
| NFR-04 | No blur, heavy glow or large filters | Required | Implemented |
| NFR-05 | Load time on a typical broadband connection | Under 2 seconds (excluding the font) | Not yet measured |

### 4.2 Usability

| ID | Requirement | Status |
| --- | --- | --- |
| NFR-06 | A visitor can discover every interaction without reading instructions | Implemented by design; needs user testing |
| NFR-07 | Touch targets are large enough to tap reliably (nose, tongue, worms) | Partly verified; worms are small on phones |
| NFR-08 | Double-tap timing is forgiving (400 ms window) | Implemented |

### 4.3 Accessibility

| ID | Requirement | Status |
| --- | --- | --- |
| NFR-09 | Visible focus outline on buttons | Implemented |
| NFR-10 | Buttons have text labels for screen readers | Implemented |
| NFR-11 | Reduced-motion preference lowers wind to 30 percent and turns off body bob and chew animations | Implemented |
| NFR-12 | Full keyboard operation of the tongue game | Pending |
| NFR-13 | Colour contrast of the title meets readable levels on the sky | Needs check |

### 4.4 Compatibility

| ID | Requirement | Status |
| --- | --- | --- |
| NFR-14 | Works in current Chrome, Edge, Safari and Firefox | Not yet tested |
| NFR-15 | Works on iOS and Android browsers in portrait and landscape | Not yet tested |
| NFR-16 | Degrades gracefully without Web Audio (silent) or without `color-mix()` (single-colour chameleon) | Implemented by design |

### 4.5 Reliability

| ID | Requirement | Status |
| --- | --- | --- |
| NFR-17 | Resizing or rotating the screen does not reset the garden or break the chameleon's position | Implemented (scaled SVG) |
| NFR-18 | No console errors on load | Syntax checked; not run in a browser |

### 4.6 Privacy and security

| ID | Requirement | Status |
| --- | --- | --- |
| NFR-19 | No personal data is collected or stored | Implemented |
| NFR-20 | No cookies, accounts or analytics | Implemented |
| NFR-21 | The only external request is the Google Fonts stylesheet | Implemented |

### 4.7 Maintainability

| ID | Requirement | Status |
| --- | --- | --- |
| NFR-22 | Code is organised into clear sections: scenery, branches, leaves, worms, chameleon, tongue, audio, input, frame loop | Implemented |
| NFR-23 | Colours and timing constants are easy to change | Partly (inline in code) |

---

## 5. External interface requirements

### 5.1 User interface

- Full-screen SVG garden, with the chameleon at bottom centre.
- Title overlay (HTML) above the scene.
- Two round buttons (top-left: replay title; top-right: sound on/off).
- Four decorative dots on the right edge.

### 5.2 Input

- Pointer events: mouse, touch and pen.
- Single tap, double-tap, click and drag.

### 5.3 Output

- Visual: SVG and CSS on screen.
- Audio: Web Audio output through the device speakers.

### 5.4 External services

- Google Fonts (`fonts.googleapis.com`) for Cinzel Decorative. Optional.

---

## 6. Open issues and decisions

| ID | Issue | Options | Owner |
| --- | --- | --- | --- |
| OI-01 | Title behaviour: settle to top (current) or fade out after 5 seconds (original brief) | Keep settle / fade out | User |
| OI-02 | Visual match: hand-built SVG (current) or use the reference image directly as the backdrop | Keep SVG / use image backdrop with interactive layer on top | User |
| OI-03 | Worm discovery: original brief asked for probability-based discovery; the user now asks for worms always present | Confirm always present / add discovery later | User |
| OI-04 | Colour sampling from artwork (FR-25) | Build now / defer | User |
| OI-05 | Hosting for a public URL | Keep private artifact link / static hosting / share publicly | User |

---

## 7. Acceptance criteria

Version 1 is accepted when:

1. Every *M* requirement marked *Implemented* is verified in at least two desktop browsers and one phone.
2. Falling leaves (FR-30 to FR-32) are implemented and verified.
3. The nose → tongue → control → catch → eat sequence works from a cold start, without a reload.
4. No console errors appear during a 5-minute session.
5. The owner signs off the open issues in §6.
