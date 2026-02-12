---
name: lora-captioner
description: Plan-first workflow for creating detailed image captions for AI/LoRA training datasets, including per-image .txt files, trigger-word inclusion, and batch processing of local image folders.
---

# LoRA Captioner

## Overview

Create high-detail, tag-style captions for image datasets used in AI/LoRA training. Always plan first, always ask for the trigger word, then caption each image and save a matching .txt file.

## Workflow (Plan First, Then Execute)

1. **Plan first**
   - State a brief plan before writing any files.
   - Confirm the target folder and image extensions.

2. **Collect required inputs**
   - Ask for the **trigger word** (do not assume or hardcode it).
   - Ask for **overwrite policy**: overwrite existing .txt, skip if exists, or write .new.txt.
   - Ask for **caption style** if not provided: high-detail comma tags (default).

3. **Enumerate images**
   - List image files in the target folder (`.png`, `.jpg`, `.jpeg`, `.webp`, `.bmp`).
   - Sort by filename for deterministic order.

4. **Caption in a continuous batch**
   - Process images sequentially without pausing unless the user requests checkpoints.
   - For each image, view it and generate a caption that includes the trigger word naturally.
   - Write the caption to a `.txt` file with the same base name as the image.

5. **Report summary**
   - Report how many captions were written, skipped, or failed.

## Caption Rules (High Detail)

Use **comma-separated tags**. Include these when visible:
- Subject and trigger word (must appear in every caption)
- Pose and body orientation
- Expression and gaze
- Outfit and accessories
- Hair style and color
- Makeup (if visible)
- Lighting (soft, harsh, natural, studio, etc.)
- Camera angle and framing (close-up, medium, side profile, etc.)
- Background/setting
- Mood or vibe (only if clearly conveyed)

Avoid guessing details not visible. Keep captions concise but rich.

## Output Rules

- Save captions as UTF-8 text in `image_base_name.txt`.
- Follow the user’s overwrite policy.
- Keep one caption per file, single line.

## Example Caption

`triggerword, close-up portrait, direct eye contact, soft smile, wavy brown hair, minimal makeup, black sleeveless top, soft natural light, plain light background`
