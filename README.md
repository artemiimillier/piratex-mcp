# Piratex MCP server: viral Reels, TikTok & Shorts trends inside your AI

[Piratex.ai](https://piratex.ai) is a trend radar for short videos and a **remote MCP server** that gives
Claude, ChatGPT, Claude Code, Cursor, VS Code and other MCP clients what they can't see on their own:
Instagram Reels, TikTok and YouTube Shorts that are taking off in your niche right now, creator
baselines, and a full breakdown of any video by link.

Ask your assistant *"What is going viral in my niche?"*, *"Why did @creator's last reel take off?"* or
*"Break down this TikTok: hook, script, comments"* and it calls Piratex for real data, then writes the
ideas and scripts itself.

```
https://piratex.ai/api/mcp
```

Streamable HTTP · OAuth 2.1 (no API key needed; key fallback available) · free plan available

---

## What it does

| Tool | What your AI gets |
|---|---|
| `trending_now` | Videos in a niche that are outperforming their own creator: views, **x to the creator's median** (views ÷ median of the creator's last 12 videos), views per hour, comment rate, hook, platform. Any niche in plain words; a niche new to the catalog is collected in 5–10 minutes (up to 50 creators). |
| `get_profile` | A creator by link or handle (Instagram, TikTok): last 12 videos with x to median for each. |
| `xray_video` | Any video by link (Reels, TikTok, YouTube Shorts, long YouTube, Instagram/TikTok posts and carousels): metrics, timed transcript, hook (first 3 s), scenes, 8 key frames, top 50 comments, the guessed comment "code word" of a DM funnel, and an `adapt` brief to remake the structure in your own style. |
| `niche_search`, `set_my_niches`, `my_profile` | Find niches in the catalog and save yours, so "my niche" just works. |
| `connect_account` | Suggest niches from your own account (when enabled). |
| `account`, `credit_history` | Plan, credits left and history (free, read-only). |

Signals worth knowing:

- **x to median**: a reel with 80k views is a hit for a creator whose videos usually get 10k (x8) and a flop
  for one who usually gets 300k. Piratex ranks by the creator-relative number, not raw views.
- **Late bloomers**: videos that came alive 2–10 days after posting.
- **Code-word funnels**: videos whose caption asks to comment a word (or whose comment rate is 3× the
  creator's usual), with the word guessed from repeated comments.

Data comes from public videos and profiles only. Piratex never logs into anyone's account and never asks
for your social media passwords. Third-party captions, transcripts and comments are returned as data,
marked untrusted, never as instructions.

## Connect

### Claude (claude.ai, Desktop, mobile)

Settings → Connectors → **Add custom connector** → paste `https://piratex.ai/api/mcp` → Add → sign in on
piratex.ai and press **Allow**. The connector then works on claude.ai, desktop and mobile.

### ChatGPT

On chatgpt.com (desktop): **Plugins** → **+** → **Add custom MCP server** (if there is no Plugins section:
Settings → Apps → Advanced → developer mode). Name `Piratex`, URL `https://piratex.ai/api/mcp`,
authentication OAuth → Create. The section may be missing on the free ChatGPT plan.

### Claude Code

```bash
claude mcp add --transport http piratex https://piratex.ai/api/mcp
```

Then run `/mcp` and sign in in the browser.

### Cursor

`~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "piratex": { "url": "https://piratex.ai/api/mcp" }
  }
}
```

### VS Code

`.vscode/mcp.json`:

```json
{
  "servers": {
    "piratex": { "type": "http", "url": "https://piratex.ai/api/mcp" }
  }
}
```

One-click install buttons for Cursor and VS Code are in your piratex.ai account. Any other client that
supports remote Streamable HTTP MCP servers with OAuth works with the same URL.

### Codex

```toml
[mcp_servers.piratex]
url = "https://piratex.ai/api/mcp"
bearer_token_env_var = "PIRATEX_API_KEY"
```

Create the key in your piratex.ai account and put it in `PIRATEX_API_KEY`.

## Example prompts

- "What's going viral in my niche this week? Show the top 10 with x to median and the hooks."
- "Here are three competitors: @a, @b, @c. Which of their recent videos outperformed, and what do they have in common?"
- "X-ray this reel: <link>. Give me the hook, the scene structure and what people ask in the comments, then adapt it to my niche."
- "Find late bloomers in fitness on TikTok."

## Pricing

Credits, one monthly pool for all requests. Free plan: 600 credits a month for a confirmed account
(plus a welcome bonus for the first 30 days). Paid plans from 2,000 RUB a month. A niche trends request
costs 20 credits, a full video x-ray 300, a creator profile 40. Failed or empty requests are refunded;
repeating the same request within 24 hours is free. Current prices: [piratex.ai/pricing](https://piratex.ai/pricing).

The website is in Russian and payments are in RUB (Russian bank cards). The tools work in any language
inside your assistant.

## Links

- Website: https://piratex.ai
- MCP server docs: https://piratex.ai/mcp-server (RU) · https://piratex.ai/en/mcp-server (EN)
- Guides: https://piratex.ai/guides
- For AI agents: https://piratex.ai/llms.txt

---

## По-русски

Piratex.ai — радар трендов Reels, TikTok и Shorts и MCP-сервер для вашего ИИ. Подключите
`https://piratex.ai/api/mcp` к Claude (Настройки → Коннекторы → «Добавить свой коннектор»), ChatGPT
или Claude Code и спросите: «Что сейчас залетает в моей нише?». ИИ получит ролики, которые набирают в
разы больше обычного для своего автора, и сможет разобрать любой ролик по ссылке: речь с таймкодами,
хук, сцены, кадры и комментарии. Подробно: [piratex.ai/mcp-server](https://piratex.ai/mcp-server),
гайды: [piratex.ai/guides](https://piratex.ai/guides).

*Instagram принадлежит компании Meta Platforms Inc., деятельность которой признана экстремистской и
запрещена на территории Российской Федерации.*

This repository contains documentation and registry metadata for the hosted Piratex MCP server; the
server itself is operated by Piratex.ai.
