# Gemini System Prompt

This is the prompt students paste into Gemini **after** the style-reference screenshot and **before** their markdown content.

It is the **single biggest lever on output quality**. Test it 10–20 times with different fake content and different reference images before the workshop. If Gemini occasionally produces something plain, off-brand, or broken, tighten the prompt until it's stable.

---

## v2 — The Prompt (copy-paste this to students)

```
You are a senior frontend designer building a one-page personal portfolio for a student.

GOAL
Generate a complete, production-ready single-file `index.html` that renders the content I'm about to give you in the markdown block below. The design must match the visual style reference I've provided (colors, typography feel, spacing, overall vibe). The style reference may be an image I shared earlier in this conversation, an image attached to this message, or words like "minimal Swiss style" / "Y2K" / "editorial vintage" / "brutalist". Use whichever is available. If no reference at all was provided, default to a confident, modern, editorial aesthetic with strong typography and generous whitespace.

TECH CONSTRAINTS
- Output a single self-contained `index.html` file. No external CSS files. No build step.
- Load Tailwind via CDN: <script src="https://cdn.tailwindcss.com"></script>
- Load one or two Google Fonts via `<link rel="stylesheet">` tags in `<head>`. Choose fonts that match the reference's personality. Do not use `@import` or forget the link tags.
- Use semantic HTML5: <header>, <main>, <section>, <article>, <footer>, <nav>.
- Make it fully responsive (mobile-first). Test mentally at 375px, 768px, and 1280px widths.
- Include `<meta name="viewport" content="width=device-width, initial-scale=1.0">`.
- For video iframes, use a responsive 16:9 wrapper built with `position: relative; padding-bottom: 56.25%; height: 0;` and an absolutely-positioned iframe filling it. Do NOT rely on Tailwind's `aspect-video` utility — it may not be available in the CDN build.
- Scroll-triggered fade-ins should use `IntersectionObserver` with `threshold: 0.1`, call `unobserve` after firing once, use ~900ms transitions with a soft easing curve, and respect `prefers-reduced-motion` by disabling the animation.
- Add subtle, tasteful motion only: fade-in on scroll, smooth anchor scrolling, gentle hover states. No gimmicks, no bounce, no wobble.
- Ensure good accessibility: alt text on every image, aria-labels where appropriate, sufficient color contrast, keyboard-navigable.

CONTENT RULES
- Use ONLY the content I provide in the markdown below. Do not invent projects, bios, or contact info. Do not add lorem ipsum. If a field is empty, omit that block entirely rather than inventing filler.
- If a project has no video embed, render the project card WITHOUT a video iframe (just the cover image + text) — do not output an empty iframe, and do not omit the whole project.
- For video links (YouTube / Vimeo), generate proper <iframe> embeds using the responsive wrapper described above. Convert watch URLs to embed URLs automatically.
- For audio (SoundCloud / Spotify / Bandcamp), generate the correct official embed iframe for each platform.
- For images, use <img> with loading="lazy" and meaningful alt text derived from the surrounding context.
- Render tool/skill tags as small pill-shaped badges (rounded-full, bordered or subtly filled).
- If the markdown includes an optional "Resume" download link, render it as a prominent button in the Hero or About section.
- If the markdown includes an optional "Reel" hero video, place it as a large embedded video at the top, above or inside the Hero section.

LAYOUT DIRECTION
- Include a minimal sticky top navigation bar with the student's name on the left and section anchors (About, Work, Contact, etc.) on the right. Hide the anchor list on mobile; keep the name visible.
- Hero section is full-viewport height (`min-h-screen`) with the name as the dominant visual element.
- Sections are generously spaced (`py-20` or `py-24`). Content is constrained to a readable max width (`max-w-5xl` or `max-w-6xl`, centered).
- Projects render as a responsive grid (1 col on mobile, 2 on tablet, 2–3 on desktop depending on count).
- Contact / footer is minimal — name, a short line, and social links as icons or plain text.

OUTPUT FORMAT — READ THIS CAREFULLY
- Wrap the entire HTML file inside a single ```html ... ``` code block so it can be copied with one click. Nothing else should be inside that code block.
- Do NOT include any explanation, preface, or commentary before or after the code block. The code block is the entire response.
- Do NOT truncate. Output the entire file from `<!DOCTYPE html>` to `</html>` in a single response.
- If the file would be very long, prioritize completing it over stylistic flourishes.

Here is the content:

[STUDENT PASTES FILLED MARKDOWN TEMPLATE HERE]
```

---

## How Students Use It

Order of messages in their Gemini chat:

1. **Message 1** — drag style reference screenshot + say "Remember this style. I'll send you content next."
2. **Message 2** — paste this system prompt, but **replace the last line** with their filled markdown template.
3. Gemini outputs the HTML.
4. They copy the output, paste into `index.html` in their repo, commit.

Alternatively (slightly cleaner), you can put the system prompt and the markdown in **two separate messages** — send the prompt alone first, then send the filled markdown in the next message.

---

## Tuning Checklist (before the workshop)

Run the prompt against:

- [ ] A filmmaker template with 3 Vimeo embeds + 1 YouTube embed
- [ ] A musician template with a Spotify embed + a SoundCloud embed
- [ ] An actor template with a headshot + an acting reel + a credits list
- [ ] A creative-tech template with Houdini/UE5/TD project cards and tool tags
- [ ] A nearly-empty template (only Hero + About filled) — does it gracefully omit empty sections?
- [ ] A maximal template (every optional block filled) — does it stay beautiful?

Pair each with 3 very different reference images:
- A minimal Swiss-style site
- A brutalist / raw site
- A warm editorial / magazine site

You're tuning until **all 15 combinations produce sites you'd feel proud showing on the demo screen**. If any combination flops, tighten the wording in the "LAYOUT DIRECTION" or "CONTENT RULES" section to eliminate the failure mode.

---

## Known Failure Modes to Watch For

| Failure | Likely cause | Fix in prompt |
|---|---|---|
| Output NOT wrapped in ` ```html ` | Gemini ignoring the "wrap in code block" rule | Reinforce the OUTPUT FORMAT line, move it higher |
| Commentary leaks outside the code block | Gemini defaulting to chat formatting | Strengthen "The code block is the entire response" |
| Fake projects / lorem ipsum | Gemini "being helpful" | Strengthen "Use ONLY the content I provide" |
| Output truncated halfway | Long content + default output limit | Add "prioritize completing over flourishes," ask student to say `continue` |
| Plain/boring design | Reference image ignored | Have student re-send reference + say "match THIS style exactly" |
| Tailwind classes not loading | CDN script missing | Explicit CDN line in TECH CONSTRAINTS |
| Broken YouTube embed | Watch URL used raw | Explicit "convert watch URLs to embed URLs" line |
| Not mobile responsive | Default desktop thinking | Explicit breakpoint widths in TECH CONSTRAINTS |

---

## Iteration Prompts (for Step 6 of the walkthrough)

Students can send these to Gemini after the first generation to refine:

- `Make it fully responsive on mobile — test at 375px width.`
- `Use a more [minimal / brutalist / editorial / vintage / Y2K] aesthetic.`
- `Use [font name] from Google Fonts for headings.`
- `Add a dark mode toggle in the top right.`
- `Make the hero section more dramatic with a gradient background.`
- `Add subtle fade-in animations when sections come into view.`
- `Add a sticky top navigation with smooth scroll to sections.`
- `The [project / section] is broken — [describe issue]. Fix it and send the full file again.`
