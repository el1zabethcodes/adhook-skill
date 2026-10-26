<div align="center">

# 🎯 AdHook

### Performance Ad Creative Angle Extractor

**Stop writing fluff copy. Ship testable creative angles.**

AdHook turns a raw offer + audience brief into a **10-angle psychological attack matrix** — every angle with a 0–3s stop-hook (visual + voiceover), a falsifiable hypothesis, and the one KPI that proves or kills it.

<p>
  <img src="https://img.shields.io/github/stars/el1zabethcodes/adhook-skill?style=flat-square" alt="Stars" />
  <img src="https://img.shields.io/badge/status-production--ready-brightgreen?style=flat-square" alt="Status" />
  <img src="https://img.shields.io/badge/tested-Claude_3.5_Sonnet-7C3AED?style=flat-square&logo=anthropic" alt="Tested on Claude 3.5 Sonnet" />
  <img src="https://img.shields.io/badge/tested-GPT--4o-412991?style=flat-square&logo=openai" alt="Tested on GPT-4o" />
  <img src="https://img.shields.io/badge/license-MIT-green?style=flat-square" alt="MIT License" />
</p>

<p><em>Built for media buyers & performance teams running</em><br>
<b>Meta (Feed / Reels) · TikTok · YouTube Shorts</b></p>

</div>

---

## 🖥️ Demo

![Demo](demo/demo.gif)

<sub>Placeholder — record a 15s generation run and drop it at <code>demo/demo.gif</code>.</sub>

**Terminal preview:**

```text
$ adhook run --offer "PM SaaS for agencies, $49/mo, unlimited seats" \
             --audience "agency owners drowning in Slack + sheets" \
             --platform meta-reels

  AdHook Engine v1.0.0
  ├─ Parsing offer ..................... USP: unlimited seats · risk reversal: 14d trial
  ├─ Profiling audience ................ dominant objection: "another tool to babysit"
  ├─ Mapping triggers .................. 10/10 anchored (loss_aversion → identity)
  └─ Engineering 0–3s hooks ............ done

  ANGLE MATRIX ─────────────────────────────────────────────────────────────
  01 LOSS AVERSION       VO [0.0s] "You're losing 11 hours a week to Slack tabs."
                         KPI: CPA vs. control                EST. IMPACT: −20%
  02 PATTERN INTERRUPT   VIS [0.0s] founder deletes the agency's Slack tab live
                         KPI: Hook Rate > 35%                EST. IMPACT: +40% hold
  03 US vs. THEM         VIS [0.0s] split-screen: 6-tool stack vs. single board
                         KPI: CTR > 1.0%                     EST. IMPACT: +25% CTR
  …
  ✔ 10 creative vectors · 3 A/B priorities ranked · kill criteria attached
  ⏱ generated in 1.4s
```

## 😴 vs 🎯 — Before / After

| Generic AI copy | AdHook Angle Matrix |
|---|---|
| "Buy our serum — it makes your skin glow instantly!" | **Pattern Interrupt** · VO: *"Stop putting moisturizer on dry skin."* · VIS: wiping product off with a timer on screen · Hypothesis: attacking a common habit beats benefit-led copy on 3s hold · **KPI: Hook Rate > 35%** |
| "Our project management software saves you time." | **Loss Aversion** · VO: *"You're losing 11 hours every week to Slack tabs."* · VIS: screen split with a calculator burning cash · Hypothesis: quantified loss outperforms a generic time-saving claim on CPA · **KPI: CPA −20%** |
| "Join thousands of happy customers!" | **Social Proof & Tribe** · VO: *"412 agencies fired their tool stack this quarter."* · VIS: counter ticking over a tool graveyard · Hypothesis: a specific many beats a vague crowd on CTR · **KPI: CTR > 1.0% (Reels)** |

## 📦 What you get

- **10 distinct psychological angles** — Loss Aversion, Pattern Interrupt, Social Proof, Us vs. Them, Extreme Contrast, Immediate Utility, Curiosity Gap, Authority, FOMO, Identity. Never two angles on the same trigger.
- **0–3s hooks, dual-channel** — a shootable first frame plus a ≤12-word voiceover line written for the ear.
- **Falsifiable hypotheses** in `If → then → because` form. No "engagement will improve" nonsense.
- **One primary KPI per angle** with a numeric target: Hook Rate / CTR / CPA / ThruPlay / CVR.
- **Top-3 A/B test priorities** and kill criteria for the losers.
- **Guardrails** — a banned-cliché list, compliance flags (`⚠ needs proof asset` instead of fabricated proof), and platform pacing notes.

Markdown table by default, or strict JSON (`format: json`) for API pipelines.

## 🚀 Quick Start

### Claude Projects

1. Create a Project → open **Custom Instructions**
2. Paste the full contents of [`skill.md`](skill.md)
3. Drop your brief into a chat: `offer: … / audience: … / platform: meta-reels`

### Cursor

```bash
# .cursor/rules/adhook.mdc  (or legacy .cursorrules) — paste skill.md, then:
# "Run AdHook on: offer=… audience=… platform=tiktok"
```

### ChatGPT Custom GPT

1. GPT Builder → **Configure**
2. Instructions = full contents of [`skill.md`](skill.md)
3. Conversation starter: `offer: …, audience: …, platform: yt-shorts`

### API

```python
from openai import OpenAI

client = OpenAI()
skill = open("skill.md", encoding="utf-8").read()

r = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "system", "content": skill},
        {"role": "user", "content": "offer: … | audience: … | platform: meta-feed | format: json"},
    ],
)
print(r.choices[0].message.content)
```

<sub>Same pattern with Anthropic: pass <code>skill.md</code> as the system prompt for <code>claude-3-5-sonnet</code>.</sub>

## 🤝 Contributing

Contributions welcome — especially:

- new triggers (keep the *one primary trigger per angle* rule),
- benchmark updates from real account data,
- translations of the banned-cliché list.

Open an issue or a PR.

## 📄 License

[MIT](LICENSE) — free for personal and commercial performance testing.
