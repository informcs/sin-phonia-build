# Sin Phonia — 2D Anime Production Roadmap

## Goal

Produce a playable, edited 2D anime episode for **Sin Phonia** with an original story, dialogue, action choreography, sound, and a final MP4 export. Use Meta AI as a creative assistant for ideation and supported image/video generation, while keeping GitHub as the source of truth for scripts, references, shot plans, prompts, and production status.

**Production principle:** do not attempt a full 10-minute episode first. Prove the visual style and continuity with a 30–60 second pilot scene, then expand shot by shot.

## Repository audit (checked before planning)

Current default branch: `main`.

The repository currently contains:
- `All sin phonia.txt` — worldbuilding, power system, factions, character relationships, and an Episode 1 draft.
- `ตัวละครsin-phoniaภาคเเรก/` — character folders with PNG reference images and text descriptions for Rin Tsukiyomi, Kaguya Akane, Homura Senka, Luminara Valuce, Meilin Zhou, Xeron Vax, Flora Nightingale, Carmen Void, Elvira Greenwood, and Long Rongchen.
- `docs/META_AI_2D_ANIMATION_BRIEF.md` — instructions for using Meta AI as a production assistant.
- `README.md` — currently only a short title.

No animation project, source video, rendering script, audio assets, or application code was visible in the inspected tree. Treat this as an **art/story reference repository**, not an existing animation pipeline. Preserve the existing lore and character references; do not reorganize or overwrite them without approval.

## Recommended production stack

- **Meta AI:** story alternatives, shot prompts, visual explorations, and short video/image generation only where the current Meta AI interface supports it. Do not assume it can write directly to this repository or generate a complete episode in one operation.
- **DaVinci Resolve or CapCut Desktop:** edit generated clips, dialogue, sound effects, music, transitions, and final MP4.
- **Krita or another image editor:** clean up stills, create overlays, and prepare character/background layers when needed.
- **Blender (optional):** camera moves, parallax, compositing, and 2.5D effects if the project needs more control.
- **GitHub:** scripts, storyboards, prompts, character reference metadata, shot manifests, and small review images. Keep large rendered video files out of ordinary Git history; use Git LFS or GitHub Releases when appropriate, subject to their current limits.

## Phased workflow

### Phase 0 — Lock the production target
1. Confirm the episode format, intended audience, language, and whether dialogue will be Thai, Japanese, or another language.
2. Start with a 30–60 second pilot, 16:9, 1080p target, and a consistent frame rate selected before editing.
3. Create a shot list and an asset manifest before generating footage.
4. Keep the existing character designs and lore as canon unless the owner approves changes.

**Exit check:** the pilot's duration, aspect ratio, language, and deliverable format are written down.

### Phase 1 — Story and screenplay
1. Use `All sin phonia.txt` as the primary canon reference.
2. Adapt the Episode 1 opening into a self-contained pilot: Rin awakens in the ruined twilight sakura garden; Soul Ink destabilizes; Akane arrives and contains the surge; end on a clear hook.
3. Write dialogue, action, emotion, and sound cues separately.
4. Avoid introducing new lore unless clearly marked as a proposal.

**Deliverables:** logline, short screenplay, scene breakdown, continuity notes.

### Phase 2 — Visual bible and continuity
1. Use each character's existing PNG and text description as the identity reference.
2. Build a one-page visual sheet per character: silhouette, face, costume, palette, power effects, and prohibited changes.
3. Create environment references for the ruined sakura garden, mirror/crystal containment field, and key lighting.
4. Keep a prompt log for every approved design and note which reference image was used.

**Deliverables:** character sheets, environment sheets, palette, approved prompt templates.

### Phase 3 — Storyboard and animatic
1. Split the 30–60 second pilot into approximately 6–12 shots.
2. For each shot, document duration, framing, camera movement, character action, background motion, dialogue, and transition.
3. Make a rough animatic using storyboard images and temporary audio before generating final clips.
4. Review pacing and screen direction; make sure every action is understandable without relying on effects alone.

**Deliverables:** storyboard, timed shot list, rough animatic.

### Phase 4 — Generate and refine footage
1. Generate one shot at a time in Meta AI (or another approved tool), not the entire sequence as one prompt.
2. Keep clips short and use the same character references, design wording, lighting language, and screen direction.
3. Generate alternate takes for difficult shots; select the clearest motion rather than the flashiest effect.
4. Check for face/costume drift, extra limbs, changing props, inconsistent hands, unstable backgrounds, and unintended text.
5. If image-to-video is unavailable or inconsistent, use layered stills with controlled camera moves and limited animation as a fallback.

**Deliverables:** selected clips, approved stills, generation prompt log, notes on fixes needed.

### Phase 5 — Edit, sound, and final render
1. Assemble selected shots in Resolve or CapCut in storyboard order.
2. Add dialogue/voice acting, ambience, impacts, music, and transitions; use only audio that is original, licensed, or otherwise permitted.
3. Mix dialogue clearly above music and sound effects.
4. Export an MP4 (H.264 is a practical compatibility target), then play it from beginning to end to verify video and audio.
5. Keep a high-quality project export and a smaller preview copy.

**Deliverables:** playable pilot MP4, editable editing project, audio/source attribution notes.

### Phase 6 — Quality check and publish
- [ ] Video opens and plays from beginning to end.
- [ ] Audio is synchronized and dialogue is understandable.
- [ ] Character identity and costume remain consistent across shots.
- [ ] No accidental black frames, broken transitions, or missing media.
- [ ] Resolution, frame rate, and duration match the agreed target.
- [ ] Credits, licenses, and AI-generated asset notes are recorded.
- [ ] The MP4 is attached to a GitHub Release or stored with Git LFS if suitable; ordinary Git history is reserved for small text and reference files.

## Suggested repository layout (add gradually)

Do not move existing files just to match this layout. Add only the folders needed for the pilot.

```text
docs/
  META_AI_2D_ANIMATION_BRIEF.md
  PRODUCTION_ROADMAP.md
  episode-01/
    screenplay.md
    storyboard.md
    continuity.md
    prompts.md
    shot-list.csv
production/
  episode-01/
    README.md
    asset-manifest.csv
    edit-notes.md
assets/
  approved/
    characters/
    backgrounds/
    sound/
renders/              # keep large renders out of normal Git history
```

## Shot-list template

Use one row per shot with these fields:

`shot_id, duration_seconds, location, characters, framing, camera, action, expression, effects, dialogue, audio, reference_assets, prompt_version, status, output_file`

Suggested status values: `planned`, `storyboarded`, `generated`, `selected`, `edited`, `approved`.

## Meta AI prompt workflow

For each shot, provide:
1. **Context:** episode, scene, preceding and following action.
2. **Identity anchors:** exact character names and approved visual references.
3. **Blocking:** who is where, what moves, and the direction of movement.
4. **Camera and timing:** shot size, movement, duration, and action beats.
5. **Look:** 2D anime linework, cel shading, palette, lighting, and effects.
6. **Continuity constraints:** costume, hair, props, screen direction, and background.
7. **Avoid:** character redesign, random camera shake, excessive particles, text/logos, and unintended style shifts.
8. **Review request:** ask Meta AI to list likely continuity risks before generating alternatives.

Meta AI can assist with creative work, but a person must review results, assemble the sequence, and verify the final export. Do not report a clip as complete until the actual file has been reviewed and played.

## First pilot: proposed 45-second beat sheet

This is a production proposal based on the existing opening, not a replacement for canon.

1. **0–6s — Establishing:** ruined twilight sakura garden, red eclipse, petals drifting; slow push-in.
2. **6–12s — Awakening:** close-up on Rin's eyes and Eclipse Ink; faint whispers build.
3. **12–19s — Power surge:** cyan Soul Ink ripples through the ground and bends nearby branches.
4. **19–25s — Entrance:** red stage-like spotlight; Akane appears above the garden.
5. **25–34s — Containment:** Blood Core crystals form a geometric barrier around Rin; alternate close-ups and a wide shot.
6. **34–41s — Confrontation:** short dialogue exchange; Rin resists while Akane remains composed.
7. **41–45s — Hook:** a green light appears in the distance, hinting at Elvira; cut to title.

## Immediate next actions

1. Confirm that the 45-second pilot is an acceptable first milestone.
2. Approve the dialogue language and whether to use voice acting or subtitles for the first cut.
3. Create `docs/episode-01/screenplay.md`, `storyboard.md`, and `shot-list.csv` on a dedicated branch.
4. Generate and review a single 4–6 second test shot before producing the remaining shots.
5. Do not merge generated assets or code into `main` until they have been reviewed.
