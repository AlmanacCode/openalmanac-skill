# Writing Guidelines

These guidelines are for writing OpenAlmanac articles. Read these before writing any article. Also read https://www.openalmanac.org/ai-patterns-to-avoid.md for specific AI writing patterns to avoid.

## Before writing

### List all sources first
Before writing a single sentence of body text, list every source you gathered during research in the YAML frontmatter. If you read it and it's relevant, include it. Don't discard sources — having more sources cited correctly is always better than fewer.

```yaml
sources:
  - url: https://example.com/article
    title: "Article Title — Publication Name"
    accessed_date: "2025-01-15"
```

### Write a pure text draft
The first draft should be pure prose with [N] citation markers. No wikilinks (`[[slug|Display Text]]`), no images (`![caption](url)`), no stub creation. Just text and citations. The linking and image agents will handle the rest after the draft is complete.

## Article structure

### Lead paragraph
The lead should be 2-4 sentences that tell the reader what the subject is and why it matters — through specific facts, not evaluative claims. A reader who only reads the lead should come away with the most important information.

Don't repeat the lead's content verbatim in the body. The lead previews; the body develops.

### Sections
Use `## Section Title` for major sections. Use `### Subsection Title` sparingly — only when a section has genuinely distinct subtopics.

Each section should add new information. If you find yourself restating facts from an earlier section, cut the repetition.

### No formulaic conclusions
Encyclopedic articles don't need a concluding section. End with the last substantive fact. Don't write "In conclusion..." or "X continues to shape..." — just stop when the information stops.

## Fact density

Every sentence should contain a specific fact the reader didn't know before. This is the single most important rule.

**Bad:** "The temple plays an important role in the community."
**Good:** "The temple draws 200,000 visitors during the nine-day Navaratri festival, with police closing the adjacent road to traffic."

If a sentence doesn't contain a fact, delete it. Commentary, interpretation, and evaluative statements ("this is significant because...") almost never earn their place. The facts speak for themselves.

## Citations

- Mark claims with [N] after punctuation: `...in 1956.[4]`
- Number sequentially starting at [1]
- Every source in the sources list must be referenced at least once in the body
- Every [N] marker in the body must have a matching source in the frontmatter
- Cite the source that actually supports the claim — not the source you happened to be reading when you wrote the sentence. Misattributed citations are the most common problem in AI-written articles.

## Tone

Write like a detailed encyclopedia that people actually enjoy reading. Not a blog post, not a press release, not an academic paper. Articles should be thorough and comprehensive — go deep on the subject, cover it from multiple angles, include the details that make it come alive. But density doesn't mean dry. The best encyclopedia articles are ones people read for fun — they learn something in every sentence and want to keep going.

- Use "is" not "serves as" or "stands as"
- Use the subject's name or pronouns, not rotating descriptors ("the professor... the researcher... the educator...")
- State facts directly without announcing their importance
- No promotional language, no inflated significance — see ai-patterns-to-avoid.md for the full list

## Infobox

Include an infobox for any article about a person, place, organization, event, or concept. The infobox goes in the YAML frontmatter.

### Header
- `image_url` — hero image, the single most representative image of the subject
- `subtitle` — short tagline (not a full sentence)
- `details` — key-value pairs for the most important quick facts (birth date, location, founded, etc.)
- `links` — external URLs (official website, Wikipedia, etc.)

### Sections
Pick the section types that fit the subject:

- **timeline** — chronological events (career history, key dates)
- **list** — key items with optional subtitles (known for, works, achievements)
- **tags** — categories or labels (genres, fields, topics)
- **grid** — image grid (gallery, team members)
- **table** — structured data with headers and rows
- **key_value** — simple key-value pairs (quick facts, statistics)

You don't need all six types. Pick 1-3 that make sense for the subject.

## Length

Go deep. Err on the side of more detail, not less. A well-sourced article on a major topic should be as thorough as a good Wikipedia article — covering history, context, specifics, different angles, notable incidents, quotes from relevant people. If you have the sourced material, include it.

Thin sections are worse than no sections. If you don't have enough sourced material for a section, either research more or leave it out.
