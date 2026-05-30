# Cerase Skills

[Anthropic SKILL.md](https://www.anthropic.com/news/agent-skills)-format
instruction packs maintained by [Cerase](https://cerase.ai) — the
privacy-first B2B AI agent appliance for Italian SMBs.

## Layout

One sub-directory per skill. Each is a self-contained skill bundle
ready to be imported by Claude Code, Cursor, or the Cerase control
plane (`/admin/skills` → "Importa da Git").

| Skill | Status | Description |
|---|---|---|
| [`deck`](./deck) | shipping | Three-stage deck generator (brief → md2 markdown → HTML/PDF) using [md2-presenter](https://pypi.org/project/md2-presenter/) and headless Chromium |

## Roadmap (lands during PoC M8)

- `knowledge-answering` — answer from a scoped source set; cite; ask
  when source set is insufficient.
- `source-to-artifact` — update/create a document from multiple
  sources; copy-first; ask before applying irreversible changes.
- `audio-handler` — route audio attachments to a transcriber MCP, use
  transcript as user prompt.
- `message-attachment-receiver` — route generic attachments to
  appropriate MCPs (OCR for images, docreader for PDFs, transcriber
  for audio).

## Use from Cerase

Out-of-the-box: every Cerase appliance ships these skills as
[core skills](https://github.com/cerase-ai/cerase/blob/main/docs/control-plane/admin-flow.md)
attached automatically to every Agent — admin does nothing.

## Use standalone (Claude Code, Cursor, …)

Each skill ships its own `install.sh` (or `bash <(curl …)` one-liner)
that lands the bundle under `~/.claude/skills/<name>/`. See the
per-skill README.

## License

MIT for the whole repo unless a per-skill `LICENSE` overrides.
