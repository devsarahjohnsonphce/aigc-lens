# AIGC Lens — the explainable AI-content detector

**Don't just get a score. See the evidence.**

AIGC Lens is a browser-only tool that estimates how likely a piece of text or an image was AI-generated — and shows *why*. Instead of a black-box number, every result comes with an evidence list a human can inspect.

Built for the **Global AI Builder's Challenge (Refactor The World)** on Devpost.

## Live demo

Open `index.html` in any modern browser — no build step, no server, no API keys. Everything runs 100% client-side; nothing you paste or upload ever leaves your device.

## What it checks

**Text mode — six measurable signals**
1. Sentence-length burstiness (humans swing between short and long sentences; AI output is statistically smoother)
2. AI cliché density — marker phrases common in LLM output, English + Chinese phrase banks, highlighted in your text
3. Connective density (over-use of tidy transition words)
4. Vocabulary diversity (type–token ratio, length-adjusted)
5. Repeated structure (recurring n-grams and sentence openings)
6. Paragraph structure (template-like, evenly sized paragraphs)

**Image mode**
- Byte-level scan for generator signatures (Stable Diffusion, Midjourney, ComfyUI markers, PNG text chunks) and camera EXIF presence
- Pixel statistics: local smoothness, noise uniformity, saturation, edge density

Three built-in samples (AI-cliché article / casual human essay / human–AI mixed draft) let you see the contrast in one click. On those samples the tool scores 65 vs. 9 — and the evidence list shows exactly why.

## Honest framing

Results are a **first-pass screening signal, never proof**. Formal human writing can score high; edited AI text can score low. The tool says so on the page, on purpose: a detection result is only useful if a human can inspect the reasoning behind it.

## Tech

Vanilla HTML / CSS / JavaScript, Canvas API, File API. One self-contained file.

## Why

Built by a graduate student researching AIGC detection, around one observation: detection is as much a communication problem as a modeling problem. A slightly weaker model whose reasoning a teacher, editor, or moderator can inspect beats a stronger black box.

## License

MIT
