# YouTube Analyzer Skill

A Claude Code skill that analyzes YouTube videos and extracts structured content based on your requests.

## What It Does

Drop a YouTube URL into Claude Code and ask for what you need:

```
"Watch https://youtube.com/... and extract a PRD for what he built"
"Analyze https://youtube.com/... and give me the recipe"
"https://youtube.com/... - summarize the key steps"
"What did they build in this video?"
```

The skill will:
1. Fetch the video transcript
2. Analyze the content based on your request
3. Generate a structured markdown document
4. Save it to your current directory

## Supported Output Types

| Type | Trigger Phrases | Output |
|------|-----------------|--------|
| **PRD** | "what did they build", "extract a PRD", "clone this" | Product Requirements Document |
| **Recipe** | "recipe", "ingredients", "how to cook" | Structured recipe with ingredients & steps |
| **Tutorial** | "tutorial", "how to", "guide", "steps" | Step-by-step guide with timestamps |
| **Summary** | "summarize", "key points", "TLDR" | Concise overview with takeaways |
| **Code** | "code", "implementation", "technical" | Code walkthrough with explanations |
| **Custom** | Any other request | Format based on your specification |

## Installation

### 1. Copy the skill folder

Copy the `youtube-analyzer` folder to your Claude Code skills directory:

```
~/.claude/skills/youtube-analyzer/
```

### 2. Configure YouTube Service (Required)

This skill requires access to YouTube transcripts. You need one of:

**Option A: Router MCP with YouTube service**

If you have router-mcp configured with YouTube actions (`get_metadata`, `get_transcript`), the skill will use it automatically.

**Option B: YouTube MCP Server**

Install a YouTube MCP server that provides transcript access.

### 3. Restart Claude Code

After installation, restart Claude Code to load the skill.

## Usage

Just share a YouTube URL and describe what you want:

```
# Extract a PRD from a tutorial video
https://youtube.com/watch?v=abc123 - extract a PRD for building this

# Get a recipe from a cooking video
Watch this and give me the recipe: https://youtube.com/watch?v=xyz789

# Summarize a long video
Summarize the key points from https://youtube.com/watch?v=def456

# Custom extraction
https://youtube.com/watch?v=ghi012 - list all the tools and resources mentioned
```

## Output

By default, files are saved to your current working directory:

```
./youtube-video-title-prd.md
./youtube-cooking-tutorial-recipe.md
./youtube-tech-talk-summary.md
```

You can specify a custom output path:

```
Extract the recipe and save to ./recipes/pasta.md
```

## File Structure

```
youtube-analyzer/
├── skill.md              # Main skill definition
├── references/
│   └── output-formats.md # Templates for each output type
└── README.md             # This file
```

## Troubleshooting

### "Video not found" or transcript errors

- Verify the URL is correct and the video is public
- Some videos don't have captions/transcripts available
- Check that your YouTube service (router-mcp or MCP server) is configured

### Skill not triggering

- Ensure the skill folder is in `~/.claude/skills/`
- Restart Claude Code after installation
- Try explicitly mentioning "analyze" or "watch" with the URL

### Large videos timing out

For very long videos (2+ hours), the transcript may be large. The skill will attempt to process in chunks, but you may need to ask for a specific section.

## Companion Skills (Optional)

After extracting content, you may want to convert it to other formats:

| Skill | Purpose |
|-------|--------|
| `to-pdf` | Convert markdown to PDF |
| `to-visual` | Create styled visual documents |
| `to-spreadsheet` | Export structured data to Excel |
| `to-presentation` | Generate slide decks |

## License

MIT License - feel free to modify and share.
