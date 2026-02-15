# Chinese Vocab

## Rules
- Set `reversible: true` for all single-word/phrase translations
- Use the JSON key as the Chinese characters (used for TTS)
- Use `front` field only when additional context is needed beyond the characters
- `back` should be English only (translation, no Chinese characters)

## Pinyin Ruby Annotations

Always use HTML `<ruby>` tags to display pinyin above Chinese characters on the `front` side. The `back` side should be English only.

### Format

Wrap **each character individually** so the pinyin aligns directly above its character:

```html
<ruby>你<rt>nǐ</rt></ruby><ruby>好<rt>hǎo</rt></ruby>
```

This renders as:

```
 nǐ   hǎo
 你    好
```

### Rules
- One `<ruby>` tag per character — never group multiple characters under one `<rt>`
- Use tone-marked pinyin (e.g. `nǐ`, not `ni3`)
- No spaces between `<ruby>` elements (the browser handles spacing)

### Example card

```json
{
  "你好": {
    "front": "<ruby>你<rt>nǐ</rt></ruby><ruby>好<rt>hǎo</rt></ruby>",
    "back": "hello",
    "created": "2025-01-15T00:00:00.000Z",
    "reversible": true,
    "tags": ["greetings"]
  }
}
```

## Tags
- `["greetings"]` — common greetings and pleasantries
- `["food"]` — food and drink vocabulary
- `["verbs"]` — action words
- `["numbers"]` — numbers and counting
- `["daily"]` — everyday conversational phrases
