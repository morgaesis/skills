---
name: temporal-browser-observation
description: Observe an interactive web page across time in an isolated automation browser. Use for actions, transitions, loading delays, hover or focus effects, animation, charts, canvas, SVG, WebGL, maps, or any visual state where one screenshot can misrepresent behavior.
---

# Temporal Browser Observation

## Contract

- Use a fresh automation-owned browser context, not the user's personal browser.
- Start frame capture before the timing-sensitive action.
- Perform the action, capture until the page visually settles or the bounded observation window expires, and inspect the final frame with the temporal trail.
- Treat a screenshot taken before settling as insufficient evidence of failure.
- Prefer visual quiet over DOM or network quiet; use DOM, network, and console signals as supporting evidence.

## Observe

1. Use Playwright or an equivalent isolated browser automation tool.
2. Capture frames at an interval suited to the expected motion.
3. Stop when recent frames are visually quiet, the maximum window expires, continuous animation is established, or a clear failure appears. Frames are visually quiet when the observed region shows no perceptible change for `quiet_ms`.
4. Create `motion_trail.png` from sampled changed regions when motion affects the conclusion, by tiling or overlaying the cropped frames in capture order (for example with Pillow or ImageMagick).
5. Crop trails to dense widgets such as charts, canvas, maps, and sliders; use the full viewport for layout transitions.
6. Preserve `final_screenshot.png` as the settled-state artifact.

Use these defaults unless the interaction needs finer or longer observation:

```yaml
max_observe_ms: 5000
frame_interval_ms: 100
trail_interval_ms: 250
max_trail_frames: 12
quiet_ms: 800
```

## Safety

- Create a temporary profile or context and close it afterward.
- Do not reuse cookies, passwords, extensions, or active sessions unless the user explicitly supplies a test profile or credentials.
- Avoid destructive actions in real accounts.
- Redact secrets from generated images when possible.

## Verify

- Report whether and when the page settled, remained animated, timed out, or failed.
- Include network or console failures only when they affect the conclusion or next action.
- Use element references for normal controls and coordinates only for custom visual surfaces.
