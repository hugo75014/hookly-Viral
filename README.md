# 🔥 Hookly — AI Viral Hooks with Virality Score

Generate viral TikTok/Reels/Shorts hooks, scripts, captions & hashtags in 10 seconds. Built-in **Virality Score (0-100)** and **6 native languages** (EN, FR, ES, DE, PT, IT).

**🌐 Live demo:** [https://ebfddchq9khj9.space.minimax.io](https://ebfddchq9khj9.space.minimax.io)

---

## ✨ Features

- 🎯 **Virality Score (0-100)** — every hook is scored on length, power words, pattern interrupt, strong start, direct address, and curiosity gap. Click the badge to see the full breakdown.
- 🌍 **6 languages** — English, French, Spanish, German, Portuguese, Italian. Power words and viral patterns native to each language (not bad translations).
- 🔌 **Multi-LLM** — works offline with the smart template engine, OR plug in your own Groq (free tier) or OpenAI key for real AI.
- 📅 **Smart scheduler** — generate content, schedule a reminder, export to Google Calendar / .ics / browser notifications.
- 🎨 **Beautiful UI** — dark theme, smooth animations, no signup, no credit card.

---

## 🚀 Quick start

```bash
# Open the file directly — that's it
open index.html

# Or serve it locally
python3 -m http.server 8000
# then open http://localhost:8000
```

That's literally it. It's a single-file static site, no build step, no dependencies.

---

## 🔑 Optional: bring your own AI key

1. Click ⚙️ in the nav
2. Pick a provider:
   - **Groq** (free tier, ultra-fast) — get a key at [console.groq.com](https://console.groq.com)
   - **OpenAI** (paid, highest quality) — get a key at [platform.openai.com](https://platform.openai.com)
3. Paste your key, Save
4. Test connection ✅

Your keys stay in your browser's localStorage. They never touch any server.

---

## 📂 Project structure

```
hookly/
├── index.html          # The entire app (HTML + CSS + JS in one file)
├── legal.html          # Terms & privacy + AI policy
├── favicon.png         # Site icon
└── README.md           # You are here
```

**Yes, it's one file.** ~175KB. Everything inline. No bundler, no framework, no backend. That's a feature, not a bug — you can host it anywhere static, including GitHub Pages, Netlify, Vercel, Cloudflare Pages, or even a USB stick.

---

## 🧠 How the Virality Score works

Pure JS, no API calls. Each hook gets scored 0-100 across 6 criteria:

| Criterion | Weight | What it checks |
|---|---|---|
| **Length** | 20 pts | 5-12 words is the sweet spot for short-form |
| **Power words** | 20 pts | High-impact words ("secret", "stop", "never"...) — language-specific lists |
| **Pattern interrupt** | 20 pts | Questions, exclamations, numbers, contradictions |
| **Strong start** | 15 pts | First word should be scroll-stopping (Stop, Why, Nobody...) |
| **Direct address** | 10 pts | Uses "you" / "tu" / "tú" to speak to the viewer |
| **Curiosity gap** | 15 pts | Opens a loop, teases without revealing |

Each criterion is language-aware — power words and strong starts are matched against native per-language lists for EN, FR, ES, DE, PT, IT.

---

## 🌐 Language system

Two independent language settings:

1. **UI language** (🌐 button in nav) — translates the entire interface. Persists in localStorage.
2. **Content language** (selector in the form) — controls which language the generated hooks are written in.

You can mix them: have the UI in Spanish and generate content in French, for example.

**Auto-detect**: when you type a topic in French, the content language auto-switches to 🇫🇷 (you'll see the "✨ Auto: Français" badge).

---

## 🎯 Add a new language

1. Add a `LANG_CONFIG.<code>` entry with `powerWords`, `strongStarts`, `personalPronouns`, `viralPatterns` etc.
2. Add a `UI_STRINGS.<code>` entry with all UI translations.
3. Add a `<div class="lang-chip" data-lang="<code>">` to the language selectors.
4. Add a `<div class="lang-chip" data-ui-lang="<code>">` to the translate modal.

The scoring engine will pick up the new language automatically.

---

## 🛠️ Tech stack

- Vanilla JS (no React, no Vue, no framework)
- Single `index.html` file (~175KB)
- `localStorage` for persistence (settings, scheduled posts, UI language)
- Groq / OpenAI APIs for LLM mode (user-provided keys, BYOK model)
- Web Push API for browser notifications
- `Intl.DateTimeFormat` for localized dates

---

## 📜 License

MIT — fork it, ship it, sell it, whatever.

---

## 🙏 Credits

Built with care for creators who don't want to stare at a blank screen.
