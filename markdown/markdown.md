# 🌟 Complete Markdown Guide

Markdown is a lightweight markup language that allows you to **easily format text**.
It is used in GitHub, GitLab, Notion, Obsidian, Reddit, and many other tools.
Here’s a quick guide with the essential elements.

---

## 📌 Headings
Use `#` (from 1 to 6) to create headings:
```markdown
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```

Display
---
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6

---

## 📌 Paragraph & Line Breaks
Simple text = paragraph.
Two spaces at the end of a line = forced line break.

Example:

This is a paragraph.

This is another paragraph.
And here, a forced line break.

---

## 📌 Line Break

In Markdown, there are two ways to force a line break (without creating a new paragraph):

### 1. Two spaces at the end of the line
```markdown
First line␣␣
Second line
```

### 2. Use `<br>`
```markdown
First line<br>
Second line
```

---

## 📌 Text Formatting
- **Bold** : `**text**` → **text**
- *Italic* : `*text*` → *text*
- ~~Strikethrough~~ : `~~text~~` → ~~text~~
- __Underline__ : `__text__` → __text__

---

## 📌 Links
```markdown
- [Google](https://google.com)
- [Link with title](https://google.com "Search engine")
```
📌 Display
- [Google](https://google.com)
- [Link with title](https://google.com "Search engine")

---

## 📌 Images
Add `!` to indicate that it’s an image, not a link.

```markdown
![Alt text](https://via.placeholder.com/150)
```
![Alt text](https://www.gravatar.com/avatar/00000000000000000000000000000000?d=robohash&f=y)

---

## 📌 Lists
### Unordered list
- Item 1
- Item 2
  - Sub-item
    - Sub-sub-item

### Ordered list
1. First
2. Second
3. Third

---

## 📌 Blockquotes
```markdown
> This is a quote.
>> This is a nested quote.
```


> This is a quote.
>> This is a nested quote.

---

## 📌 Code
### Inline
`inline code`

### Code block
```php
public function (Dev $me) {
    do {
        exec($me->code() . " > /dev/null &");
    }
    while (
        $me->soul()->is(SoulEnum::Alive->value)
    );
}
```

---

## 📌 Tables
```markdown
| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Row 1    | Value A  | Value B  |
| Row 2    | Value C  | Value D  |
```

---

## 📌 Separator
```markdown
---
```
