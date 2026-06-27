# guptaishika25.github.io

My personal portfolio. Live at [guptaishika25.github.io](https://guptaishika25.github.io).

I am a product manager who builds. This site is where I keep the proof: an agentic AI system that ships a podcast every morning, a few product teardowns, and two Claude skills I made for my own job hunt.

## What's here

- **AI Newsroom**, my flagship build. Six AI agents on the Claude Agent SDK that scout, fact-check and narrate a daily AI news podcast on their own. Read the [case study](https://guptaishika25.github.io/newsroom.html) or the [code](https://github.com/GuptaIshika25/ai-newsroom).
- **Case studies** on product thinking, including a WalletHub teardown and an honest report on vibe-coding a live S&P 500 dashboard.
- **Two Claude skills** I built and use: a resume tailor and a cold-outreach drafter.
- **The podcast player** on the homepage plays the latest AI Newsroom episode, which auto-publishes here every day.

## How it's built

A single static page, no framework. Plain HTML, CSS and a little JavaScript, hosted free on GitHub Pages.

```
index.html       the portfolio
newsroom.html    the AI Newsroom case study
audio/           latest.mp3 and episode.json, pushed daily by the AI Newsroom repo
images/          photos and graphics
```

Every morning the [ai-newsroom](https://github.com/GuptaIshika25/ai-newsroom) workflow produces a new episode and pushes the audio plus a small manifest into `audio/`, so the player on the homepage always has the freshest brief.

## Contact

[Email](mailto:guptais6@msu.edu) · [LinkedIn](https://www.linkedin.com/in/ishika-gupta/) · [GitHub](https://github.com/GuptaIshika25)
