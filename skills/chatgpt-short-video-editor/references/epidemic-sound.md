# Epidemic Sound music workflow

Read this reference only when the user requests Epidemic Sound music or asks
the editor to select background music automatically.

## Connection boundary

Use the official Epidemic Sound MCP server through callable tools supplied by
the active AI client. A paid subscription does not prove that the client is
connected. Confirm the tools needed for the requested workflow, normally music
search and track download; duration adaptation may require additional beta
tools.

The official remote MCP endpoint is:

`https://www.epidemicsound.com/a/mcp-service/mcp`

Authentication may use supported OAuth or `EPIDEMIC_SOUND_API_KEY`. Keep API
keys and OAuth tokens in the AI client's secure connector settings or process
environment, never in this Skill, Git, `edit/`, commands, chat, or logs. API
keys may expire; verify the live connection instead of trusting a saved setup.

If the MCP connection is missing, stop before search or download. Hand the
environment gap to `chatgpt-video-editing-setup`. Do not scrape the consumer
website or invent a download URL as a fallback.

## Automatic selection

Translate the approved direction brief into a search profile:

- story purpose and audience;
- mood and energy curve;
- speech density and whether vocals are acceptable;
- BPM range and featured instruments when useful;
- target duration and important output-timeline beats;
- platform and the user's stated publishing channel/account context.

Search the catalog and compare several viable results internally. When the
user delegated selection, choose one best-fit track using editorial fit,
dialogue compatibility, duration/adaptation fit, and musical structure. Include
the recommended title, artist, recording ID, duration, BPM, vocals state, and
reason in the plain-language strategy. Strategy approval also approves that
specific track; a materially different replacement needs renewed approval.

## Download and adaptation

After strategy approval:

1. Download only the selected recording in the approved format and stem.
2. Prefer a full instrumental mix or instrument stem for speech-heavy videos.
3. If track adaptation is available and useful, request the exact target
   duration and align a musical payoff to the video's hook, reveal, or CTA.
4. Store the asset under `edit/audio/music/`.
5. Write `music-selection.json` with track metadata, search profile, selected
   format or stem, adaptation details, and selection rationale.
6. Write `music-license-context.md` with the user's stated subscription,
   publishing account/channel context, and any safelist status actually
   verified. State that this is a production record, not legal advice or an
   independent license certificate.

## Mix and QA

Keep dialogue primary. Use musical fades, dialogue-aware ducking or automation,
and a clean ending. Inspect the rendered preview around music entrances,
exits, cuts, title impacts, product reveals, and the CTA. Measure integrated
loudness and true peak, compare effect/music level to nearby speech, and reject
any mix that masks words, clips, pumps noticeably, or ends abruptly.

Do not publish or safelist a channel unless the user separately asks for that
external account change.
