# Pappadam Breakage Simulator

A self-contained, intentionally useless entertainment feature that estimates where an uploaded pappadam may break.

## Files

- `index.html` - standalone feature markup and accessible controls.
- `pappadam.css` - cartoon food styling scoped under `.pappadam-*` classes.
- `pappadam.js` - browser-only image loading, canvas analysis, prediction overlay, games, reset, and download.

## Run independently

Open `pappadam-simulator/index.html` directly in a browser. A static server also works, for example:

```text
python -m http.server
```

Then visit `/pappadam-simulator/`.

## How prediction works

The uploaded image is decoded locally in the browser. A temporary canvas samples pixel brightness and color contrast across the image. Dark/high-contrast irregular regions influence the predicted point, angle, breakability score, personality, explanation, and verdict. The result is deliberately approximate and does not claim scientific certainty. No image is uploaded anywhere and no API key is used.

## Integration later

The module can be mounted as a route, iframe, or copied into an existing page. Keep the `.pappadam-page` root and `.pappadam-*` classes so the CSS stays isolated. The JavaScript currently initializes against the IDs in `index.html` and exposes no required global API; integration can later wrap initialization in a mount function if the host app needs lifecycle control.

The feature has no dependency on the Food Mood Predictor and does not modify its files.
