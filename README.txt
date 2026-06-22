ASCENT — Practice Console (PWA)
================================

A contemplative practice console. Run timed sessions structured by the
five-stage ascent anatomy (settle -> concentrate -> ascend -> observe/test
-> return), log what arose, and track streaks, cumulative minutes, and a
per-vehicle breakdown. Fully offline; data is stored locally in your browser.

Files
-----
  index.html      the app
  manifest.json   PWA manifest (name, icon, install metadata)
  sw.js           service worker (offline caching)


HOW TO RUN
==========
A PWA must be SERVED over http(s) -- service workers and "install" do not work
from a file:// path. localhost counts as a secure origin, so a local server is
all you need.

Option A — Python (already installed on most machines)
  1. Open a terminal in this folder.
  2. Run:   python3 -m http.server 8000
  3. Open:  http://localhost:8000
  4. In Chrome/Edge, click the "install" button in the app header
     (or the install icon in the address bar).

Option B — Node
  1. npx serve -l 8000        (or: npx http-server -p 8000)
  2. Open the URL it prints.

Option C — Any static host
  Upload the three files to Netlify / Vercel / GitHub Pages / your own server
  (served over https) and open the URL. Then install from the browser.

After the first load it runs fully offline and your data persists between
sessions on that browser/device.


NOTES
=====
- Open it via http://localhost..., NOT by double-clicking index.html.
- The app icon is an inline SVG, which Chromium installs fine. If your specific
  browser refuses the install prompt, add real 192x192 and 512x512 PNG icons to
  the "icons" array in manifest.json.
- The IBM Plex Mono font loads from Google Fonts when online and falls back to
  your system monospace font when offline.
- Data lives in this browser's localStorage. Use the Stats tab's Export button
  to back it up to a JSON file, and Import to restore or move it to another
  device.
