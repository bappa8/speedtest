# Internet Speed Test Website

A dark, colorful internet speed test website with a neon-style UI.

This project shows:
- **Ping**
- **Download speed**
- **Upload speed**
- **Live server/client network details**
- A **START / TESTING / AGAIN** action card

The design uses a **very dark theme**, glowing colors, and four equal-sized cards:
1. Ping
2. Download
3. Upload
4. Start/Test button

---

## Preview

Main visual style:
- Deep black / navy background
- Orange title
- Cyan ping card
- Green download card
- Purple upload card
- Blue testing/start card
- Footer text:
  - `© Bappa Ghosh. All rights reserved.`

---

## Features

### UI Features
- Modern dark glass-like design
- Bright neon color accents
- Responsive layout
- Equal-sized metric cards
- Smaller result number font for better balance
- Hover and testing animations on the action button

### Functional Features
- Real browser-based speed test
- Displays measured:
  - ping
  - download bandwidth
  - upload bandwidth
- Detects current network details and shows:
  - server/edge location info
  - client public IP info
  - city / region / country when available
  - ASN / network organization when available

---

## Project Files

```text
.
├── index.html
└── README.md
```

### `index.html`
Contains everything in one file:
- HTML structure
- CSS styles
- JavaScript logic

### `README.md`
This documentation file.

---

## How It Works

The page has four main cards:

### 1. Ping Card
Shows current measured ping in **ms**.

### 2. Download Card
Shows measured download speed in **Mbps**.

### 3. Upload Card
Shows measured upload speed in **Mbps**.

### 4. Action Card
Acts as the control button:
- `START`
- `TESTING`
- `AGAIN`
- `RETRY`

---

## Live Data Sources Used in the Website

The website uses a combination of sources for speed and metadata.

### Speed Test Engine
It loads the Cloudflare speed test module through jsDelivr:
- `@cloudflare/speedtest`

This is used to measure real:
- latency
- download bandwidth
- upload bandwidth

### Network Detail Sources
The page attempts to detect live network details using:
- `https://www.cloudflare.com/cdn-cgi/trace`
- `https://ipv4-check-perf.radar.cloudflare.com/api/info`
- fallback: `https://ipwho.is/`

These help fill the server and client detail lines.

---

## Server and Client Details Shown

The website tries to show:

### Server
Example format:
```text
Server: www.cloudflare.com · SIN
```

### Client
Example format:
```text
Client: Dhaka, Dhaka, BD · 203.x.x.x · ASN 12345 · ISP Name
```

If network metadata cannot be loaded, fallback text is shown.

---

## Notes About Running the Website

## Recommended way
Run it in a normal browser with internet access.

Best options:
- open from a local web server
- upload to static hosting
- open in a browser environment that allows external requests

### Recommended local server options

#### Python
```bash
python -m http.server 8000
```
Then open:
```text
http://localhost:8000
```

#### VS Code Live Server
If using VS Code, you can use the **Live Server** extension and open `index.html`.

---

## Important Arena Preview Note

Inside some sandboxed previews, external network access can be blocked.

If that happens:
- speed values may not load
- server/client details may not load
- the button may show retry/error behavior

In that case, test the site in:
- Chrome
- Edge
- Firefox
- a live hosted environment

---

## Button States

The action button changes automatically based on test state.

### `START`
Initial ready state.

### `TESTING`
Shown while a test is running.

### `AGAIN`
Shown when a test finishes successfully.

### `RETRY`
Shown if the speed test could not be started or failed.

---

## Responsive Behavior

The layout adapts to different screen sizes.

### Desktop
- Four cards in a row
- Equal height and balanced spacing

### Tablet / Smaller screens
- Grid adjusts automatically

### Mobile
- Cards stack vertically
- Sizes and padding reduce for smaller screens

---

## Design System

### Color Usage
- **Orange**: main title
- **Cyan**: ping
- **Green**: download
- **Purple**: upload
- **Blue**: action/test button

### Theme Style
- Extra dark background
- Soft glowing highlights
- Glassy panels
- Neon borders and text glow

---

## Customization Guide

You can easily edit the theme inside the `:root` CSS block.

### Main variables
```css
:root {
  --ping: #32ddff;
  --download: #4cff9f;
  --upload: #bf7cff;
  --action: #66b8ff;
}
```

### Change title color
Search for the `h1` style and update:
```css
color: #ff9b3d;
```

### Change card size
Search for:
```css
.metric {
  min-height: 240px;
}
```

### Change number size
Search for:
```css
.number {
  font-size: clamp(2rem, 3.3vw, 3rem);
}
```

### Change button size
Search for:
```css
.again-btn {
  min-height: 240px;
}
```

---

## Speed Test Measurement Config

The current speed test setup uses multiple steps to estimate connection performance.

Inside the JavaScript section, the test uses these measurement types:
- latency packets
- small download checks
- larger download checks
- upload checks

This helps provide more realistic values than a fake animation.

---

## JavaScript Overview

Main functions used:

### `setStatus()`
Updates the status message area.

### `setValue()`
Formats and prints metric values.

### `safeCall()`
Safely calls result methods from the speed test engine.

### `parseTrace()`
Parses Cloudflare trace text into key/value data.

### `fetchJson()` and `fetchText()`
Helpers for loading external metadata.

### `updateMetrics()`
Updates ping / download / upload values on screen.

### `refreshMeta()`
Refreshes server and client detail lines.

### `runTest()`
Starts the speed test.

### `stopUi()`
Resets button state when the test finishes or fails.

---

## Troubleshooting

### Problem: Server/client details show fallback text
Possible reasons:
- preview environment blocks network access
- endpoint request failed
- CORS or sandbox restrictions

### Problem: Speed test does not start
Possible reasons:
- external module could not load
- internet access is restricted
- browser blocked remote script/module requests

### Problem: Button stays in testing state
Possible reasons:
- speed test engine failed silently
- network request did not finish
- CDN/module failed to load fully

### Fix suggestions
- open the page in a normal browser
- use a local server instead of opening from a restricted preview
- check browser console for network errors
- verify internet access is active

---

## Browser Support

Recommended browsers:
- Google Chrome
- Microsoft Edge
- Mozilla Firefox

Modern browser features used include:
- ES modules
- `fetch()`
- CSS gradients
- `backdrop-filter`
- async/await

---

## Footer

The site includes this footer text:

```text
© Bappa Ghosh. All rights reserved.
```

---

## License / Usage

This project was created as a custom website file for the user request.

If you want to reuse or modify it:
- update colors as needed
- update footer text if ownership changes
- review external service usage if deploying publicly

---

## Future Improvement Ideas

Possible next upgrades:
- add jitter
- add packet loss
- add history of previous tests
- add animated charts
- add light/dark mode toggle
- add server selection
- save results to local storage
- export results as image or PDF

---

## Quick Start

1. Save `index.html`
2. Save `README.md`
3. Run a local server
4. Open the site in browser
5. Click **START**
6. View real ping, download, upload, and network details

---

## Author Notice

Footer credit used in the website:

**© Bappa Ghosh. All rights reserved.**
