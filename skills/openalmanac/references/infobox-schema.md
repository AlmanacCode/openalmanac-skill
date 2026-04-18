# Infobox schema — exact shapes

Every field below is enforced by the backend pydantic validator (`src/schemas/infobox_schemas.py`). Extra fields are rejected. Wrong types are rejected. Use these shapes exactly.

---

## Top-level shape

```yaml
infobox:
  header:      # optional — defaults to empty HeaderBlock
    ...
  sections: [] # optional — defaults to []; each item is one of the 6 section types below
```

Both `header` and `sections` have defaults. You can omit either or both. You cannot add any other top-level key.

---

## HeaderBlock

```yaml
header:
  image_url: "https://..."              # optional string URL (or null)
  subtitle:  "Short factual tagline"    # optional string (or null)
  details:                              # optional list; each entry is {key, value}
    - key: "Born"
      value: "1988, Tulsa, Oklahoma"    # VALUES MUST BE STRINGS — no ints, no dates, no objects
  links: []                             # optional list of STRING URLs only — no {url,label} objects
```

Rules:
- Every `details[i].value` **must be a string**. Wrap numbers in quotes: `value: "1882"`.
- `links` is **list of strings (URLs only)**. If you want labeled links, use a `list` section below. Do not put `{url, label}` objects in `header.links`.
- No other keys allowed in `header`.

---

## Sections (pick from EXACTLY these 6 types)

Every section has:
```yaml
type:  "<one-of: timeline | list | tags | grid | table | key_value>"
title: "Section title"
items: ...  # shape depends on type (below)
```

No other section `type` values are allowed. `"links"` is NOT a valid type — use `list` instead (see below).

### 1. timeline

```yaml
- type: timeline
  title: "Key dates"
  items:
    - primary:     "Graduates from Duke University"   # REQUIRED string — the main label
      secondary:   "B.S. in Biology"                  # optional
      period:      "2010"                             # optional — the date/year field
      location:    "Durham, NC"                       # optional
      description: ["extra details as list of strings"] # optional list[str]
      link:        "https://..."                      # optional
```

Rules:
- `primary` is **required**. Every other field is optional.
- `description` is a **list of strings**, not a single string. Wrap a single detail as `["detail"]`.
- Do NOT use `date`, `title`, `subtitle`, `text`, `label` — those are not valid fields on TimelineItem.

### 2. list

```yaml
- type: list
  title: "Notable works"
  items:
    - title:       "My First Million"                  # REQUIRED string
      subtitle:    "Podcast co-hosted with Sam Parr"   # optional
      year:        "2019"                              # optional
      description: ["list of strings"]                 # optional list[str]
      link:        "https://www.mfmpod.com/"           # optional URL
```

Rules:
- `title` is **required**.
- This is the section type to use for labeled links (use `title` as the label, `link` as the URL).

### 3. tags

```yaml
- type: tags
  title: "Topics"
  items: ["string", "string", "string"]    # list of STRINGS only
```

Rules:
- `items` is a flat `list[str]`. No objects, no nesting.

### 4. grid

```yaml
- type: grid
  title: "Investments"
  items:
    - title:       "Airbnb"                     # REQUIRED string
      image_url:   "https://..."                # optional
      year:        "2012"                       # optional
      description: "Led Seed round"             # optional — single STRING (not a list)
      link:        "https://..."                # optional
      type:        "Seed"                       # optional — investment type, product category, etc.
```

Rules:
- `title` is **required**.
- `description` here is a **single string** (different from timeline/list — those use list[str]).

### 5. table

```yaml
- type: table
  title: "Career"
  items:
    headers: ["Company", "Role", "Years"]       # REQUIRED non-empty list[str]
    rows:
      - cells: ["Twitch", "Sr. Director", "2019-2021"]
      - cells: ["Bebo",   "CEO",          "2015-2019"]
```

Rules:
- `items` is an **object** (`{headers, rows}`), not a list.
- `headers` must be a non-empty `list[str]`.
- Each row is `{cells: list[str]}`.

### 6. key_value

```yaml
- type: key_value
  title: "Specs"
  items:
    - key:   "Weight"
      value: "14 kg"       # string
```

Rules:
- Same shape as `header.details`. Each item is `{key, value}` — both strings.
- This is the **only** section type the frontend currently renders visibly in the infobox body.

---

## Summary table

| Type | Items shape | Required per item | Notes |
|------|-------------|-------------------|-------|
| `timeline` | `list[TimelineItem]` | `primary` | use `period` for the date |
| `list` | `list[ListItem]` | `title` | use this for labeled URL lists |
| `tags` | `list[str]` | — | flat strings only |
| `grid` | `list[GridItem]` | `title` | `description` is a single string |
| `table` | `{headers: list[str], rows: list[{cells: list[str]}]}` | `headers` non-empty | items is an object, not a list |
| `key_value` | `list[KeyValueItem]` | `key`, `value` | the only type currently rendered |

---

## Common mistakes to avoid

1. **Using `"links"` as a section type.** There is no `links` section type. Use `list` with `{title: label, link: url}`.
2. **Putting objects in `header.links`.** `header.links` is `list[str]`. For labeled links, use a `list` section.
3. **Using `{date, title, subtitle}` on timeline items.** The correct fields are `{primary, secondary, period}`.
4. **Putting a single string in `description` on timeline/list items.** It's `list[str]`. Wrap as `["single detail"]`.
5. **Putting numbers in `header.details[i].value`.** It's `str` — wrap as `"1882"`.
6. **Adding a `label` or `text` field on a timeline item.** Not in the schema. Use `primary`.

If the schema doesn't describe what you want, **do not invent a new field or type**. Fold the information into an existing shape (usually `key_value` or `list`).
