---
name: market-intelligence
description: Monitor the AI ecosystem (YouTube, HN, Reddit) for relevant updates. Automatically scans configured feeds and reports significant changes.
---

# Market Intelligence Skill

Automated monitoring of the AI/OpenClaw ecosystem using blogwatcher.

## Setup

```bash
# Install blogwatcher
go install github.com/Hyaxia/blogwatcher/cmd/blogwatcher@latest

# Add key feeds
blogwatcher add "HN: openclaw" "https://hnrss.org" --feed-url "https://hnrss.org/newest?q=openclaw"
blogwatcher add "Creator Magic" "https://youtube.com/@CreatorMagicAI" \
  --feed-url "https://www.youtube.com/feeds/videos.xml?channel_id=UC08Fah8EIryeOZRkjBRohcQ"

# Schedule daily scan (OpenClaw cron)
openclaw cron add "market-scan" "0 9 * * *" "Run blogwatcher scan and report"
```

## Channels Monitored

- Creator Magic (OpenClaw P-PROSPERITY content)
- NetworkChuck (mainstream tech)
- HackerNews openclaw mentions
- Reddit r/ClaudeAI + r/LocalLLaMA
- OpenClaw GitHub releases
