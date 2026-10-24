# Korea public procurement MCP — Narajangteo (G2B) bid notices

A remote MCP server that lets Claude, ChatGPT and other AI apps search Korean public bid notices and read their attachments.
Nothing to install and no data.go.kr API key — add one URL to your AI app and sign in.

```
https://work-api.00data.kr/mcp
```

Sources: Narajangteo (KONEPS / G2B) and Nuri-jangteo from the Public Procurement Service, the Defense Acquisition Program Administration (D2B),
and the e-procurement sites of LH, K-water, KEPCO and KOGAS. Notices and answers are in Korean.

## What it does

- **Search notices** by keywords, category, budget, region, deadline, contract method and more. Closed notices include award results.
- **Read attachments** — tender documents (HWP, HWPX, PDF, Word, Excel) come back as Markdown with tables intact.
- **Similar notices and past awards** — who won similar contracts and at what price.
- **Saved searches, favorites and your profile** — save a search from the chat and it shows up on the [Gonggong-ilgam](https://work.00data.kr) website, with new notices marked.

## Connect

- **Claude**: Settings → Connectors → Add custom connector → paste the URL → Connect → sign in → Allow.
- **ChatGPT**: Settings → Apps → Advanced → turn on Developer mode → Create app → paste the URL → connect from the Plugins tab.
  If you see "OAuth callback data is missing", press Connect once more.
- **Claude Code**: `/plugin marketplace add 00data-kr/narajangteo-mcp` then `/plugin install gonggongilgam@00data-kr`,
  or `claude mcp add --transport http gonggongilgam https://work-api.00data.kr/mcp`.
- **Gemini CLI**: `gemini extensions install https://github.com/00data-kr/narajangteo-mcp`
- **Cursor, VS Code and others**: add the URL as a remote (HTTP) MCP server.

## Tools

| Tool | What it does | Kind |
|---|---|---|
| `search_notices` | Search notices, with counts | read |
| `get_notice` | One notice: budget, deadline, eligibility, attachments, award result | read |
| `read_document` | Full text of an attachment | read |
| `find_similar_notices` | Similar notices and past winners / prices | read |
| `my_filters` · `save_filter` · `delete_filter` | Saved searches | read · write · delete |
| `my_favorites` · `save_favorite` · `remove_favorite` | Favorites with folders and notes | read · write · delete |
| `my_profile` · `save_profile` | Your eligibility (region, licenses), instructions and AI memory | read · write |

## Free to use

Sign in with a Kakao or Google account and it's free.

## Privacy

- You choose read / write / delete permissions when connecting and can change them or disconnect any time.
- Your conversations with the AI are not sent to us.

Issues: https://github.com/00data-kr/narajangteo-mcp/issues
