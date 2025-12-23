---
name: youtube-analyzer
description: Analyze YouTube videos and extract structured content. This skill should be used when users share a YouTube URL and ask to analyze, watch, extract, or summarize video content. Supports extracting PRDs, recipes, tutorials, summaries, code walkthroughs, and custom formats based on user request.
---

# YouTube Analyzer

Analyze YouTube videos and extract structured content based on user requests.

## When This Skill Applies

This skill activates when the user:
- Shares a YouTube URL and asks to analyze, watch, or extract content
- Requests a specific output format (PRD, recipe, tutorial, summary, etc.)
- Asks what was built, taught, or demonstrated in a video

## Process

### Step 1: Fetch Video Content

To analyze a YouTube video:

1. Extract the video ID from the URL (supports youtube.com and youtu.be formats)
2. Use router-mcp YouTube service to fetch:
   - `get_metadata` - title, channel, description, duration
   - `get_transcript` - full video transcript

```javascript
// Example: Fetch via router-mcp
route_request({
  service: "youtube",
  action: "get_metadata",
  params: { url: "<youtube-url>" }
})

route_request({
  service: "youtube",
  action: "get_transcript",
  params: { url: "<youtube-url>" }
})
```

### Step 2: Determine Output Type

Based on the user's request, identify the appropriate output format:

| User Request | Output Type | Template |
|--------------|-------------|---------|
| "extract a PRD", "what did they build" | PRD | Product Requirements Document |
| "give me the recipe", "ingredients" | Recipe | Structured recipe format |
| "tutorial", "how to", "steps" | Tutorial | Step-by-step guide |
| "summarize", "key points" | Summary | Concise overview |
| "code", "implementation" | Code Walkthrough | Technical breakdown |
| Custom request | Custom | User-specified format |

See `references/output-formats.md` for detailed templates.

### Step 3: Analyze and Extract

Process the transcript to extract structured content:

1. Identify key sections, timestamps, and topics
2. Extract relevant information based on output type
3. Organize into the appropriate template structure
4. Include relevant quotes or timestamps where helpful

### Step 4: Generate Output

Create a well-structured markdown document:

1. Include video metadata header (title, channel, URL)
2. Apply the appropriate template from `references/output-formats.md`
3. Ensure content is complete and actionable

### Step 5: Save and Display

1. **Save to file**: `./youtube-<sanitized-title>-<type>.md` in current directory
   - Sanitize title: lowercase, replace spaces with hyphens, remove special chars
   - Example: `./youtube-how-to-build-an-ai-agent-prd.md`

2. **Display summary**: Show key highlights in conversation

3. **User override**: If user specifies output path, use that instead

## Output File Format

```markdown
# [Video Title]

**Source**: [YouTube URL]
**Channel**: [Channel Name]
**Duration**: [Duration]

---

[Content based on output type template]

---

*Extracted from YouTube video using youtube-analyzer skill*
```

## Handling Large Transcripts

For videos with transcripts exceeding context limits:

1. Read transcript in chunks if saved to file
2. Use documentation-reader-specialist agent for analysis
3. Synthesize findings into the requested format

## Error Handling

If video analysis fails:
- Check if URL is valid and accessible
- Verify router-mcp YouTube service is available
- Inform user of any transcript availability issues (some videos lack captions)

## Related Skills

After extraction, users may want to convert output to other formats:
- PDF conversion (if to-pdf skill available)
- Visual document creation (if to-visual skill available)
- Spreadsheet export (if to-spreadsheet skill available)
