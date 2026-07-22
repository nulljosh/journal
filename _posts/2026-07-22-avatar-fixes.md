---
layout: post
title: "Avatar & Polish"
date: 2026-07-22 23:30:00 -0700
categories: journal nightly
---

![July 22 Evening](/assets/2026-07-22-evening.svg)

## Wednesday

Spent the evening tracking down a finicky dark-mode rendering bug on the portfolio site. The memoji avatar image had a faint white halo ring around it in dark mode, visible in Chrome on macOS but invisible in Safari. Root cause turned out to be non-premultiplied alpha on the PNG's transparent edge pixels—when the browser downscales the image during rendering, the light RGB values on the transparent edges get blended against the dark background, creating a visible glow. Fixed it by premultiplying the alpha channel in the PNG so transparent pixels store (0,0,0,0) instead of (255,255,255,0), then pushed to main. The fix auto-deployed via GitHub Pages and the halo is gone.

Collected git activity across 18 repos and found 124 commits landed in the last 12 hours across the codebase. Most repos got roadmap-prune passes; the real work was Epiphany (17 commits, landing page fixes + auth gate + local map pins), Echo (8 commits, font swaps and Mac submission), and infrastructure work (wiki-refresh fixes, roadmap sync across the board). Portfolio just needed that one image fix to ship.

Updated the journal with tonight's work and refreshed the wiki to catch up with current app states.

## Apps Summary

**Active:** Epiphany (v2.6.1 live, landing page + auth + map fixes), Talli (iOS 3.5.7 submitted 07-21, v3.5.6 live), Echo (Mac 1.3.3 waiting, iOS 1.3.3 fixed 07-22), Lexly (1.1.1 waiting), Litigate (1.0.1 submitted 07-21), Inkpress (1.0.2 waiting), Healstack (1.0 waiting), Sparkjar (Mac 1.0 submitted). **Infrastructure:** Portfolio icon fix live, 12 apps on Cloudflare Pages as of 07-21, journal/inkpress split complete.
