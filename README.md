**English** | [中文](README.zh-CN.md)

# AI Builders Brief

**Your daily AI industry intelligence, curated from the people actually building things.**

An AI agent skill that monitors 25+ top AI builders on X/Twitter, 6 leading podcasts,
and official company blogs — then delivers a curated brief in your preferred language
and channel. No API keys required.

> Follow builders with original opinions, not influencers who regurgitate.

## What You Get

A daily or weekly brief delivered to your preferred messaging app (Telegram, Discord,
WhatsApp, etc.) with:

- Key posts and insights from 25 curated AI builders on X/Twitter
- Summaries of new episodes from 6 top AI podcasts
- Highlights from official AI company blogs (Anthropic Engineering, Claude Blog)
- Direct links to all original content
- Available in English, Chinese, or bilingual

## Quick Start

### One-line install (recommended)
```bash
npx skills add wen-novarca/ai-builders-brief
```
Works with Claude Code, Cursor, Codex, and other agents.

### Manual install
```bash
# Claude Code
git clone https://github.com/wen-novarca/ai-builders-brief.git ~/.claude/skills/ai-builders-brief
cd ~/.claude/skills/ai-builders-brief/scripts && npm install

# OpenClaw
git clone https://github.com/wen-novarca/ai-builders-brief.git ~/skills/ai-builders-brief
cd ~/skills/ai-builders-brief/scripts && npm install
```

Then say **"set up ai builders brief"** or invoke `/ai-builders-brief`. The agent
walks you through setup conversationally — no config files to edit.

The agent will ask you:
- How often you want your brief (daily or weekly) and what time
- What language you prefer (English, Chinese, or bilingual)
- How you want it delivered (Telegram, email, or in-chat)

No API keys needed — all content is fetched centrally.
Your first brief arrives immediately after setup.

## Changing Settings

Your delivery preferences are configurable through conversation. Just tell your agent:

- "Switch to weekly briefs on Monday mornings"
- "Change language to Chinese"
- "Make the summaries shorter"
- "Show me my current settings"

The source list (builders and podcasts) is curated centrally and updates
automatically — you always get the latest sources without doing anything.

## Customizing the Summaries

The skill uses plain-English prompt files to control how content is summarized.
You can customize them two ways:

**Through conversation (recommended):**
Tell your agent what you want — "Make summaries more concise," "Focus on actionable
insights," "Use a more casual tone." The agent updates the prompts for you.

**Direct editing (power users):**
Edit the files in the `prompts/` folder:
- `summarize-podcast.md` — how podcast episodes are summarized
- `summarize-tweets.md` — how X/Twitter posts are summarized
- `summarize-blogs.md` — how blog posts are summarized
- `digest-intro.md` — the overall brief format and tone
- `translate.md` — how English content is translated to Chinese

These are plain English instructions, not code. Changes take effect on the next brief.

## Default Sources

### Podcasts (6)
- [Latent Space](https://www.youtube.com/@LatentSpacePod)
- [Training Data](https://www.youtube.com/playlist?list=PLOhHNjZItNnMm5tdW61JpnyxeYH5NDDx8)
- [No Priors](https://www.youtube.com/@NoPriorsPodcast)
- [Unsupervised Learning](https://www.youtube.com/@RedpointAI)
- [Data Driven NYC](https://www.youtube.com/@DataDrivenNYC)
- [AI & I by Every](https://www.youtube.com/playlist?list=PLuMcoKK9mKgHtW_o9h5sGO2vXrffKHwJL)

### AI Builders on X (25)
[Andrej Karpathy](https://x.com/karpathy), [Swyx](https://x.com/swyx), [Josh Woodward](https://x.com/joshwoodward), [Kevin Weil](https://x.com/kevinweil), [Peter Yang](https://x.com/petergyang), [Nan Yu](https://x.com/thenanyu), [Madhu Guru](https://x.com/realmadhuguru), [Amanda Askell](https://x.com/AmandaAskell), [Cat Wu](https://x.com/_catwu), [Thariq](https://x.com/trq212), [Google Labs](https://x.com/GoogleLabs), [Amjad Masad](https://x.com/amasad), [Guillermo Rauch](https://x.com/rauchg), [Alex Albert](https://x.com/alexalbert__), [Aaron Levie](https://x.com/levie), [Ryo Lu](https://x.com/ryolu_), [Garry Tan](https://x.com/garrytan), [Matt Turck](https://x.com/mattturck), [Zara Zhang](https://x.com/zarazhangrui), [Nikunj Kothari](https://x.com/nikunj), [Peter Steinberger](https://x.com/steipete), [Dan Shipper](https://x.com/danshipper), [Aditya Agarwal](https://x.com/adityaag), [Sam Altman](https://x.com/sama), [Claude](https://x.com/claudeai)

### Official Blogs (2)
- [Anthropic Engineering](https://www.anthropic.com/engineering) — technical deep-dives from the Anthropic team
- [Claude Blog](https://claude.com/blog) — product announcements and updates from Claude

## How It Works

1. A central feed is updated daily with the latest content from all sources
   (blog articles via web scraping, YouTube transcripts via Supadata, X/Twitter via official API)
2. Your agent fetches the feed — one HTTP request, no API keys
3. Your agent remixes the raw content into a digestible brief using your preferences
4. The brief is delivered to your messaging app (or shown in-chat)

See [examples/sample-digest.md](examples/sample-digest.md) for what the output looks like.

## Requirements

- An AI agent (Claude Code, OpenClaw, Cursor, or similar)
- Internet connection (to fetch the central feed)

That's it. No API keys needed. All content is fetched centrally and updated daily.

## Privacy

- No API keys are sent anywhere — all content is fetched centrally
- If you use Telegram/email delivery, those keys are stored locally in `~/.follow-builders/.env`
- The skill only reads public content (public blog posts, public YouTube videos, public X posts)
- Your configuration, preferences, and reading history stay on your machine

## Credits

Created by [Zara Zhang](https://x.com/zarazhangrui) ([zarazhangrui](https://github.com/zarazhangrui)).
Original project: [follow-builders](https://github.com/zarazhangrui/follow-builders).

## License

MIT
