# HH Goa ’26 — Frame & Builder Pass Generator 🌴

Drop a photo into either output — get **both** branded graphics, live, on a single page:

1. 🎫 **The Builder Pass** — a portrait “backstage lanyard” badge (1080×1350):
   full-bleed beach art, woven straps + metal clip, cream pass, circular photo
   ring, name in italic serif, zig-zag **builder-class tape**, holographic foil
   sticker, vertical `#FrameInGoa`, and a centered perforated **ADMIT ONE** stub
   with a serial number generated from your name.
2. ⭕ **The PFP** — an editorial “sun-halo poster” (1080×1080): brand sun disc +
   rays setting into the sea behind your photo, `Hacker House ✦ Goa` masthead in
   italic serif, official beach art strip, and the manifesto pill
   *Less noise · More signal · #FrameInGoa*.

Built for the HH Goa 2026 shortlisting task. 100% client-side: no login, no signup,
no server round-trips — upload to finished graphics in seconds. Everything gets a
subtle film-grain finish for a printed-badge feel.

## Run it

Static site — serve the folder with anything:

```bash
py -m http.server 8000    # then open http://localhost:8000  (no-cache static server)
```

Deploy by dropping the folder on GitHub Pages / Netlify / Vercel / Cloudflare Pages.

## Features → requirements map

| Requirement | How it's handled |
|---|---|
| **One pass, no gates** | Tap/click the photo ring on either output to upload — each output keeps its **own photo + framing**, both render live, side by side on one page |
| **JPG / PNG / HEIC** | `heic2any` converts iPhone HEIC in-browser; drag & drop a file straight onto either canvas |
| **No manual cropping** | Cover-fit + drag-to-reposition + pinch zoom, or scroll-wheel zoom **inside the ring** (page scrolls normally outside it) — portrait, landscape and off-center shots all fit |
| **Personalized** | Name, stack/role, auto-generated *Builder Class* (🎲 reroll), serial number derived from your name |
| **Near-instant** | Client-side Canvas; pre-cropped art strips; bundled fonts (~250 KB total media) |
| **On-brand** | Official green #036735 / sun-yellow #FDDB04, official hhgoa.com art (beach, गोवा lockup, HACKER HOUSE serif wordmark, builders illustration), serif × mono typography |
| **1-click download** | Real PNGs per format |
| **Working share flow** | One Share action, no saving: phones open the X share sheet with **both images attached**; desktop opens X instantly with the pre-filled post (caption + `#FrameInGoa`) — attach the ↓ PNGs |
| **Mobile-friendly** | Stacked layout, tap-to-upload, touch pan + pinch zoom |

## Files

```
index.html            the whole app (UI + Canvas renderers, no build step)
serve.py              no-cache static server (Cache-Control: no-store)
assets/
  sunrise.jpg         official HH Goa beach art (compressed)
  goa_hindi.svg       official "गोवा" lockup
  hackerhouse.png     official HACKER HOUSE wordmark (page header)
  hackers.jpg         official builders illustration (page footer banner)
  heic2any.min.js     HEIC → JPEG conversion (bundled, no CDN)
  fonts/              Instrument Serif + Space Grotesk + JetBrains Mono (bundled woff2)
examples/             rendered outputs
```

## Tweet copy used by Share

> got my builder pass + pfp for Hacker House Goa 2026 🌴🎫 — *name, class*
> AI × Crypto residency · Goa, India · 28–31 Oct
> Make yours 👉 *link*
> #FrameInGoa
