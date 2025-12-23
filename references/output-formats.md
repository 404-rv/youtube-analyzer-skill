# Output Format Templates

Templates for different content extraction types from YouTube videos.

---

## PRD (Product Requirements Document)

Use when: User asks "what did they build", "extract a PRD", "clone this project", etc.

```markdown
# PRD: [Project Name]

## Overview

[1-2 sentence description of what was built]

**Source**: [Video Title] by [Channel]
**Video**: [URL]

---

## Problem Statement

[What problem does this solve? Why was it built?]

---

## Solution

[High-level description of the solution]

| Component | Purpose |
|-----------|---------|
| [Component 1] | [What it does] |
| [Component 2] | [What it does] |

---

## Technical Architecture

### Tech Stack
- **[Category]**: [Technology]
- **[Category]**: [Technology]

### Data Flow
[Describe the flow of data through the system]

---

## Implementation Details

### [Major Component 1]

**Trigger**: [What starts this]

**Process**:
1. [Step 1]
2. [Step 2]
3. [Step 3]

### [Major Component 2]

[Repeat structure as needed]

---

## Configuration Requirements

### Credentials/APIs Needed
- [API/Service 1]
- [API/Service 2]

### Setup Steps
1. [Setup step 1]
2. [Setup step 2]

---

## Implementation Checklist

- [ ] [Task 1]
- [ ] [Task 2]
- [ ] [Task 3]

---

## Notes

- [Key insight 1]
- [Key insight 2]
```

---

## Recipe

Use when: User asks for "recipe", "ingredients", "how to cook", etc.

```markdown
# [Recipe Name]

**Source**: [Video Title] by [Channel]
**Video**: [URL]

---

## Overview

[Brief description of the dish]

| | |
|---|---|
| **Prep Time** | [Time] |
| **Cook Time** | [Time] |
| **Total Time** | [Time] |
| **Servings** | [Number] |
| **Difficulty** | [Easy/Medium/Hard] |

---

## Ingredients

### Main Ingredients
- [ ] [Amount] [Ingredient]
- [ ] [Amount] [Ingredient]

### For the [Component] (if applicable)
- [ ] [Amount] [Ingredient]

### Seasonings & Spices
- [ ] [Amount] [Ingredient]

---

## Equipment Needed

- [Equipment 1]
- [Equipment 2]

---

## Instructions

### Prep
1. [Prep step 1]
2. [Prep step 2]

### Cooking
1. [Cooking step 1]
2. [Cooking step 2]

### Assembly/Finishing
1. [Final step 1]
2. [Final step 2]

---

## Tips & Notes

- **Pro tip**: [Tip from video]
- **Substitution**: [Alternative ingredient option]
- **Storage**: [How to store leftovers]
```

---

## Tutorial

Use when: User asks for "tutorial", "how to", "guide", "steps", etc.

```markdown
# Tutorial: [Topic]

**Source**: [Video Title] by [Channel]
**Video**: [URL]
**Duration**: [Length]

---

## Overview

[What this tutorial teaches]

### What You'll Learn
- [Learning outcome 1]
- [Learning outcome 2]
- [Learning outcome 3]

### Prerequisites
- [Prerequisite 1]
- [Prerequisite 2]

---

## Step-by-Step Guide

### Step 1: [Title]
**Timestamp**: [MM:SS]

[Detailed instructions]

### Step 2: [Title]
**Timestamp**: [MM:SS]

[Detailed instructions]

### Step 3: [Title]
**Timestamp**: [MM:SS]

[Detailed instructions]

---

## Key Concepts

### [Concept 1]
[Explanation]

### [Concept 2]
[Explanation]

---

## Common Mistakes to Avoid

1. **[Mistake]**: [How to avoid it]
2. **[Mistake]**: [How to avoid it]

---

## Next Steps

- [What to learn next]
- [How to practice]
```

---

## Summary

Use when: User asks for "summary", "key points", "overview", "TLDR", etc.

```markdown
# Summary: [Video Title]

**Source**: [Channel]
**Video**: [URL]
**Duration**: [Length]

---

## TL;DR

[2-3 sentence summary of the entire video]

---

## Key Points

1. **[Point 1]**: [Brief explanation]
2. **[Point 2]**: [Brief explanation]
3. **[Point 3]**: [Brief explanation]
4. **[Point 4]**: [Brief explanation]
5. **[Point 5]**: [Brief explanation]

---

## Main Takeaways

- [Actionable takeaway 1]
- [Actionable takeaway 2]
- [Actionable takeaway 3]

---

## Topics Covered

| Topic | Timestamp | Key Insight |
|-------|-----------|-------------|
| [Topic 1] | [MM:SS] | [Insight] |
| [Topic 2] | [MM:SS] | [Insight] |
| [Topic 3] | [MM:SS] | [Insight] |

---

## Who Should Watch

This video is best for:
- [Audience type 1]
- [Audience type 2]

Skip if:
- [Reason to skip]
```

---

## Code Walkthrough

Use when: User asks about "code", "implementation", "technical details", programming topics.

```markdown
# Code Walkthrough: [Topic]

**Source**: [Video Title] by [Channel]
**Video**: [URL]

---

## Overview

[What this code does / what problem it solves]

### Technologies Used
- [Language/Framework 1]
- [Language/Framework 2]
- [Library 1]

---

## Project Structure

project/
  [file1]     # [Purpose]
  [file2]     # [Purpose]
  [folder]/
    [file3]   # [Purpose]

---

## Key Code Sections

### [Section 1 Name]
**Purpose**: [What this does]

**Explanation**:
- [Line-by-line or block explanation]

### [Section 2 Name]
**Purpose**: [What this does]

**Explanation**:
- [Explanation]

---

## How It Works

1. [Step 1 of the flow]
2. [Step 2 of the flow]
3. [Step 3 of the flow]

---

## Key Functions/Methods

| Function | Purpose | Parameters |
|----------|---------|------------|
| [function1] | [What it does] | [params] |
| [function2] | [What it does] | [params] |

---

## Common Issues & Solutions

| Issue | Solution |
|-------|----------|
| [Issue 1] | [Fix] |
| [Issue 2] | [Fix] |
```

---

## Custom Format

Use when: User specifies a custom output format not covered above.

Follow these principles:
1. Include video metadata header (title, channel, URL)
2. Structure content logically for the requested format
3. Use markdown formatting (headers, lists, tables, code blocks)
4. Be complete but concise
5. Include timestamps where relevant
6. End with a footer noting the source
