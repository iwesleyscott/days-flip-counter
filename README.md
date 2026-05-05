# days-flip-counter

A split-flap (Solari board) style countdown widget. Displays the number of days remaining until a target date. Hosted via GitHub Pages and embeddable as an `<iframe>` in Confluence, Notion, or any web page.

---

## Demo

```
https://iwesleyscott.github.io/days-flip-counter/
```

---

## Usage

The widget is a single `index.html` file with no dependencies or build step. All configuration is done via URL query parameters.

### Basic

```
https://iwesleyscott.github.io/days-flip-counter/
```

Displays a countdown to **365 days from today** using default green brand colors.

### With a target date

```
https://iwesleyscott.github.io/days-flip-counter/?d=20270101
```

---

## Query Parameters

All parameters are optional. Unrecognized or invalid values fall back silently to defaults.

### `d` — Target date

| | |
|---|---|
| Format | `YYYYMMDD` |
| Default | 365 days from today |
| Example | `d=20270101` |

```
?d=20261221
```

---

### `bg` — Page background color

| | |
|---|---|
| Format | 3 or 6 character hex, `#` optional |
| Default | `2e2e2e` |
| Example | `bg=444444` |

```
?bg=ffffff
?bg=fff
?bg=2e2e2e
```

---

### `board` — Flip board background color

Controls the background color of the board panel that surrounds the flip tiles.

| | |
|---|---|
| Format | 3 or 6 character hex, `#` optional |
| Default | `444444` |
| Example | `board=696969` |

```
?board=4a4a4a
```

---

### `tilecolor` — Flip tile background color

Controls the background color of the individual flip digit tiles. The bottom half of each tile is rendered slightly darker automatically.

| | |
|---|---|
| Format | 3 or 6 character hex, `#` optional |
| Default | `3a3a3a` (top) / `2e2e2e` (bottom) |
| Example | `tilecolor=333333` |

```
?tilecolor=222222
```

---

### `numcolor` — Flip number color

Controls the color of the digits displayed on the flip tiles.

| | |
|---|---|
| Format | 3 or 6 character hex, `#` optional |
| Default | `73d700` (Fancy Green) |
| Example | `numcolor=ffffff` |

```
?numcolor=73d700
```

---

### `numsize` — Flip number font size

Controls the font size of the digits in pixels.

| | |
|---|---|
| Format | Integer (px) |
| Range | `12` – `120` |
| Default | `46` |
| Example | `numsize=38` |

```
?numsize=52
```

---

### `labelcolor` — Label text color

Controls the color of all label text: "days remaining", "days", and the target date line.

| | |
|---|---|
| Format | 3 or 6 character hex, `#` optional |
| Default | `8fde33` / `abe766` (Fancy Green variants) |
| Example | `labelcolor=ffffff` |

```
?labelcolor=abe766
```

---

### `labelsize` — Label text size

Scales all label text relative to the default size.

| | |
|---|---|
| Format | Integer (%) |
| Range | `50` – `300` |
| Default | `100` |
| Example | `labelsize=120` |

```
?labelsize=80
```

---

### `scale` — Board scale

Resizes the entire board element proportionally using CSS `transform: scale()`. Does not affect surrounding page layout, making it suitable for constrained `<iframe>` embeds.

| | |
|---|---|
| Format | Integer (%) |
| Range | `10` – `300` |
| Default | `100` |
| Example | `scale=75` |

```
?scale=85
```

---

### `shadow` — Toggle shadows

Controls box shadows on the board, tiles, and screws, and the number glow effect on the canvas.

| | |
|---|---|
| Format | `0` = off, omit = on |
| Default | on |
| Example | `shadow=0` |

```
?shadow=0
```

---

## Examples

### Default Green branding
```
https://iwesleyscott.github.io/days-flip-counter/
```

### Green branding, lighter palette, shadows off
```
https://iwesleyscott.github.io/days-flip-counter/?bg=444444&board=696969&tilecolor=4a4a4a&numcolor=73d700&labelcolor=abe766&shadow=0
```

### Light theme
```
https://iwesleyscott.github.io/days-flip-counter/?bg=faf8f0&board=e0ddd6&tilecolor=c8c4bc&numcolor=444444&labelcolor=696969&shadow=0
```

### Custom date, scaled down for a narrow embed
```
https://iwesleyscott.github.io/days-flip-counter/?d=20270101&scale=75&shadow=0
```

---

## Confluence iFrame Embed

```html
<iframe
  src="https://iwesleyscott.github.io/days-flip-counter/?d=20270101&bg=444444&board=696969&tilecolor=4a4a4a&numcolor=73d700&labelcolor=abe766&shadow=0"
  width="320"
  height="220"
  frameborder="0"
  scrolling="no">
</iframe>
```

> **Note:** Confluence Cloud restricts iFrame sources. An administrator must add `github.io` to the allowed iFrame hosts list under **Settings > Security > Allowed iFrame Hosts**.

---

## Deployment

1. Fork or create a new public repository named `days-flip-counter`
2. Add `index.html` to the repository root
3. Go to **Settings > Pages > Source: main branch / root > Save**
4. The widget will be live at `https://iwesleyscott.github.io/days-flip-counter/` within ~60 seconds

No build tools, dependencies, or configuration files required.

---

## Browser Support

All modern browsers. Canvas 2D API required (supported in all browsers since 2013).

---

## License

MIT
