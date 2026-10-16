# Pacha Satta: Task List

**Last updated:** 2026-10-16
**Key:** `[x]` done · `[~]` built, needs testing · `[ ]` not started · `(D)` decision needed from owner

---

## Stage 1: Garden scene and chameleon

- [x] Sky, clouds, distant mountains, waterfalls and valley backdrop
- [x] Canopy layout that frames the top and edges, leaving a clear sky window
- [x] Branches: main, secondary and twigs, with a bark-coloured faceted look
- [x] Leaves in layered shades, with back, middle and foreground depths
- [x] Flowers scattered along branches
- [x] Fruit: large single fruit and grape-like clusters
- [x] Chameleon drawn as hand-authored facets, bottom centre, on the perch branch
- [x] Eyes: two pupils with spring tracking, idle wander
- [x] Colour by touch: chameleon body, branch, leaf, fruit, flower
- [x] Colour easing and facet shading preserved
- [x] Wind alternating left and right, with gusts
- [x] Small leaves and flowers sway; branches stay still
- [x] Responsive: scene scales to any screen; chameleon stays bottom centre

## Stage 2: Environment polish

- [ ] **Falling leaves**: detach, drift, rotate, sway, recycle (FR-30 to FR-32)
- [ ] Vary falling-leaf speed, size and phase so no two move alike
- [ ] Limit the number of falling leaves on screen
- [ ] Gentle leaf tap reaction tuned (kick strength and settle time)
- [ ] Flower petals sway with a slight delay from their stems

## Stage 3: Worms and tongue

- [x] Natural segmented worms on fruit and branches
- [x] Worms wiggle and creep
- [x] Nose tap shows tongue for 1.5 seconds
- [x] Double-tap tongue enters control mode
- [x] Tongue follows the pointer across the whole screen
- [x] Tongue tip catches a worm and pulls it back
- [x] Chewing animation and sound on eating
- [x] Control ends on second double-tap or 4 seconds idle
- [x] Respawn of eaten worms after 22 to 40 seconds
- [~] Touch control: double-tap and drag on a phone (needs device test)
- [ ] Keyboard control of the tongue (NFR-12)
- [ ] Clearer cue when a worm is caught (subtle sound and a small visual)
- [ ] Worm hit area enlarged on small screens
- [ ] `(D)` Confirm: worms always present, or add discovery rules later (OI-03)

## Stage 4: Sound

- [x] Procedural airflow that pans left and right over 20 seconds
- [x] Leaf rustle, branch creak, fruit bite and chew, tongue flick, catch plip, munch
- [x] Ambient rustles and creaks while playing
- [x] Sound starts on first tap; mute button in top-right
- [~] Loudness balance across all sounds (needs listening test)
- [ ] Headphone check for panning

## Stage 5: Title and interface

- [x] Title centred on load with sprout icon
- [x] Title settles to the top after 5 seconds
- [x] Replay button (top-left)
- [x] Mute button (top-right)
- [x] Decorative dots on the right edge
- [ ] `(D)` Title: keep settle-to-top, or fade out after 5 seconds (OI-01)
- [ ] Check title contrast on the sky at every screen size (NFR-13)

## Stage 6: Visual match to reference

- [ ] `(D)` Choose: keep hand-built SVG, or use the reference image as the backdrop (OI-02)
- [ ] Refine the chameleon's head, eyes and tail shape against the reference
- [ ] Adjust valley and waterfall tones to match the reference
- [ ] Add remaining small details seen in the reference (distant birds, small blossoms)
- [ ] Final colour pass for vibrancy on phones (bright screens)

## Stage 7: Colour from artwork (optional)

- [ ] `(D)` Build pixel sampling from the rendered scene, or defer (OI-04)
- [ ] If built: palette as fallback when sampling fails
- [ ] If built: test that sampled colours never produce a dull chameleon

## Stage 8: Testing

- [ ] Run in Chrome, Edge, Safari and Firefox on desktop (NFR-14)
- [ ] Run on iPhone and Android in portrait and landscape (NFR-15)
- [ ] Check console for errors during a 5-minute session (NFR-18)
- [ ] Measure frame rate on a mid-range laptop and phone (NFR-01)
- [ ] Check frame cost does not grow over 10 minutes (NFR-02)
- [ ] Check page load time on a typical connection (NFR-05)
- [ ] Check reduced-motion setting (NFR-11)
- [ ] Check the page with sound off and with Web Audio blocked (NFR-16)
- [ ] Check the title font falls back cleanly with no network (NFR-16)
- [ ] User testing with five people who have not seen the page: note where they get stuck

## Stage 9: Accessibility

- [x] Visible focus outline on buttons
- [x] Text labels on buttons
- [x] Reduced-motion support (wind and animation)
- [ ] Keyboard control of the tongue game (NFR-12)
- [ ] Screen-reader description of the scene reviewed

## Stage 10: Delivery

- [x] Single-file build: `index.html`
- [x] Published link for private viewing
- [x] Documentation: README, SRS, task list, assets list
- [ ] `(D)` Public hosting: keep private link, or host as a static page (OI-05)
- [ ] Final version number and changelog entry
- [ ] Owner sign-off on the acceptance criteria in SRS §7

---

## Current priorities

1. Falling leaves (Stage 2), the largest missing feature
2. Testing on real phones and browsers (Stage 8), to find what breaks
3. Owner decisions marked `(D)`, so the visual and title work can be finished
