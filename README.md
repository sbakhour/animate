# Animate — Bring your photo to life

Upload a photo. Describe what should happen. Get a real, AI-generated cinematic video in minutes — no editing skills, no subscription.

**Live product:** https://animate.bakhour.ca

## What it does

You upload a photo and describe what should happen in it — clouds drifting, a camera slowly zooming, light shifting — and Animate generates a real short video from that photo using [Wan 3](https://replicate.com/alibaba/wan-3), a state-of-the-art image-to-video model.

- 5-second video, 720p
- Vertical (9:16), landscape (16:9), or square (1:1) — pick the format for TikTok, Reels, Shorts, YouTube, or desktop
- Delivered on a private link only you have, usually within 3–4 minutes
- One-time payment, CA$9.99 — no subscription, no account required

## Try it free first

The [live site](https://animate.bakhour.ca) shows a real source photo and the real generated video from this exact pipeline before you pay anything — not stock demo content, not someone else's showcase. Both are included in this repo: [source.jpg](source.jpg) → [demo.mp4](demo.mp4).

## How it works (high level)

```
Upload a photo, describe what should happen
      ↓
Pay securely via Stripe Checkout
      ↓
Signed payment confirmation triggers generation
      ↓
Real video generated from your photo (Wan 3, ~3–4 minutes)
      ↓
Private result page — watch, download
```

A few things worth knowing if you're technically curious:

- **Payment first, always.** Generation only ever starts after Stripe cryptographically confirms your payment went through — never before, and never twice for the same order.
- **No card details touch our servers.** Checkout happens entirely on Stripe's own hosted page.
- **Your photo is validated, not just accepted.** Uploads are checked against real image formats before anything is stored; nothing you upload becomes publicly listed or guessable.
- **Generation takes real time.** Video generation isn't instant — a 5-second clip takes a few minutes to render. The order page shows live status: awaiting payment → generating → complete.
- **Bounded and honest.** If generation genuinely can't complete, the order is marked as needing attention — you're never left in the dark, and never falsely told something is ready when it isn't.

## Privacy

Your photo, prompt, and the resulting video are stored privately, tied to a unique, unguessable order link — not indexed, not listed anywhere public. All are automatically deleted 30 days after your order.

## Use cases

- Bringing an old or favorite photo to life for a short, original clip
- A moving portrait or scene for social content
- Adding subtle motion — light, weather, camera movement — to a still photo
- Something fun, nostalgic, or just for the "whoa, that's real?" of it

We don't promise views, engagement, or how content performs anywhere it's shared — Animate generates the video; what you do with it is up to you.

## About

Animate is built and operated by [ProfitCollector](https://api.bakhour.ca), which also runs a handful of other machine- and human-payable tools, including its sibling text-to-video product [Imagine](https://github.com/sbakhour/imagine). This project focuses specifically on making a genuinely good photo-to-video experience — not a general AI platform.

---

*Not affiliated with Alibaba or the Wan model authors beyond using their publicly available model via Replicate's API. Source photo by [Sven Pieren](https://unsplash.com/@svenlp) via [Unsplash](https://unsplash.com), used under Unsplash's free commercial-use license.*
