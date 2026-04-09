# Local LLM Hardware Matcher — Gemma 4 Edition

> **Can your PC or Mac run Gemma 4 locally?** Stop guessing VRAM requirements. Enter your hardware specs and get an instant, personalized setup recommendation.

🔗 Live: `gemma-4-local-hardware-requirements`  
🏷️ Keywords: `gemma 4 local`, `gemma 4 ollama`, `gemma 4 requirements`

---

## Overview

A highly converting, SEO-optimized Single Page Application (SPA) that helps developers figure out if and how they can run Google's Gemma 4 locally. The interactive hardware matcher provides tailored recommendations for model variant, quantization, and inference framework based on the user's specific device.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | Astro (static SEO shell) |
| Interactivity | React (`.tsx`) via `client:load` |
| Styling | Tailwind CSS + shadcn/ui |
| Theme | Dark (`slate-900` background) |
| Language | English only |

---

## Features

- **Auto-detect OS** via `navigator.userAgent` on mount
- **Interactive Matcher Tool** — inputs: OS / System RAM / GPU VRAM / Primary Goal
- **Dynamic Result Card** with:
  - Usability badge: 🟢 Great / 🟡 Usable / 🟠 Experimental / 🔴 Not Recommended
  - Recommended model + quantization
  - Human-readable reasoning
  - Speed estimate + framework
  - One-click CLI copy block or App Store buttons
  - Community confidence score
- **Evergreen SEO Sections**: Model tiers, frameworks, community FAQ

---

## Supported Model Profiles (Cold-Start Data)

| ID | Hardware Target | Goal | Recommendation | Rating |
|---|---|---|---|---|
| `g4-mobile-general` | iOS ≥6GB RAM | Any | Gemma 4 E2B/E4B via PocketPal | 🟡 Usable |
| `g4-mac-coding` | Mac ≥24GB RAM | Coding | Gemma 4 31B Q4_K_M via Ollama/MLX | 🟡 Usable |
| `g4-pc-sweetspot` | Windows ≥12GB VRAM | Chat | Gemma 4 26B-A4B MoE Q4_K_M | 🟢 Great |
| `g4-pc-low-vram-long` | Windows 8GB VRAM | Long Context | Gemma 4 E4B Q6_K via llama.cpp | 🟠 Experimental |

---

## Project Structure

```
/
├── src/
│   ├── pages/
│   │   └── gemma-4-local-hardware-requirements/
│   │       └── index.astro       # SEO shell + static sections
│   ├── components/
│   │   └── HardwareMatcher.tsx   # React interactive tool (client:load)
│   └── data/
│       └── modelDatabase.ts      # ModelProfile[] type + cold-start data
└── public/
```

---

## Matching Algorithm

```ts
findBestMatch({ os, ram, vram, primaryGoal })
// 1. Filter by OS + minRam + minVram thresholds
// 2. Find exact primaryGoal match
// 3. Fallback to primaryGoal: 'any' | 'chat' for the hardware tier
```

---

## SEO Targets

- **Title:** `Gemma 4 Local Hardware Matcher: Can Your PC/Mac Run It?`
- **H1:** `Run Gemma 4 Locally: The Hardware Matcher`
- **Meta description:** Stop guessing VRAM requirements. Use our interactive hardware matcher...
- **Top keywords:** `gemma 4 ollama`, `gemma 4 gguf`, `gemma 4 26b a4b`, `gemma 4 mlx`, `gemma 4 requirements`

---

## Competitor Reference

- [Gemmamatch](https://www.gemmamatch.com)

---

## Related Notes

- [[gemma 4 local]] — SEO research & Google Trends analysis
- [[Local LLM Hardware Matcher & Guide (Gemma 4 Edition MVP)]] — Full PRD

---

你需要我把这个 README 直接写入某个项目目录，还是有其他调整？
