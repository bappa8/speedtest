# speedtest
A real-time internet speed test tool built with HTML, CSS &amp; JavaScript. Tests ping, jitter, download &amp; upload speed using Cloudflare's speed server.

# ⚡ Speed Test
A lightweight, real-time internet speed test web app built with pure HTML, CSS, and JavaScript — no frameworks, no dependencies.

## 🌐 Live Demo
👉 https://bappa8.github.io/speedtest/

## 📌 Features
- **Ping** — measures your latency to the test server in milliseconds
- **Jitter** — measures connection stability (variation in ping)
- **Download Speed** — tests how fast data is received (Mbps)
- **Upload Speed** — tests how fast data is sent (Mbps)
- **Server Info** — detects the test server location and ISP
- **Client Info** — detects your IP, city, country, and ISP
- **Live Speedometer** — animated gauge that moves in real time during the test
- Works on all browsers including Firefox, Chrome, Edge, and Safari

## 🛠️ Built With
- HTML5 & CSS3
- Vanilla JavaScript (no libraries)
- Canvas API (speedometer gauge)
- Cloudflare Speed Test API (`speed.cloudflare.com`)
- Resource Timing API (accurate upload measurement)

## 🚀 How It Works
1. Detects your server and client info automatically
2. Sends multiple HEAD requests to measure ping and jitter
3. Downloads chunks of data (1MB, 5MB, 10MB) to measure download speed
4. Uploads chunks of data (0.5MB, 1MB, 2MB) to measure upload speed
5. Displays all results in a clean, real-time dashboard
