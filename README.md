# LoRA Captioner Skill for Codex

Create rich, high-detail captions for LoRA training images. The skill plans first, asks for your trigger word, and writes matching .txt files for each image.

## What This Skill Does

- Prompts for the trigger word (never hardcodes it)
- Generates detailed, comma-tag captions
- Writes a .txt file with the same base name as each image
- Supports batch captioning without pauses

## Install

### Option A: Install with the Skill Installer (official)

Run this in your Codex terminal:

```
$skill-installer --repo sienadrayy/lora-captioner-skill --path . --name lora-captioner --method download
```

After installation, restart Codex to pick up the new skill.

### Option B: Clone + Copy

Clone this repo and copy the folder into your Codex skills directory under `local/lora-captioner`.

### Option C: Download ZIP + Copy

Download the repo ZIP, extract it, and copy the extracted folder into your Codex skills directory under `local/lora-captioner`.

## Use It

In Codex, say something like:

```
Use the lora-captioner skill to caption all images in this folder.
```

The skill will:
1. Plan first
2. Ask for your trigger word
3. Generate detailed captions and save .txt files

## Repo Structure

- SKILL.md - skill definition
- agents/openai.yaml - agent configuration

## Notes

- Captions are single-line, comma-separated tags
- The trigger word appears in every caption
- Backgrounds, lighting, pose, expression, and outfit are included when visible
- `SKILL.md` should be saved as UTF-8 **without BOM** to avoid skill loader errors
