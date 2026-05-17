---
name: obsidian-markdown
description: |
  Obsidian Flavored Markdown 작성·편집. wikilink, embed, callout, properties 등 옵시디언 전용 문법 지원.
    P1: obsidian, 옵시디언, wikilink, 위키링크, callout, 콜아웃, frontmatter, embed, 임베드, obsidian markdown, 옵시디언노트, 옵시디언문서, 옵시디언파일, 옵시디언작성, 옵시디언편집, 위키링크문법, 콜아웃문법, properties, 프로퍼티, vault, 볼트, 옵시디언문법, OFM.
    P2: 만들어줘, 작성해줘, create, write, edit, 옵시디언 파일 만들어줘, 옵시디언으로 작성해줘, wikilink 써줘, callout 추가해줘, 옵시디언 노트 생성해줘.
    P3: Obsidian Flavored Markdown, wikilink syntax, callout blocks, frontmatter properties, obsidian embed syntax.
    P4: 옵시디언 노트 작성·편집시, 위키링크·콜아웃·임베드 문법이 필요할 때.
    P5: .md로, 옵시디언노트로.
    NOT: 일반마크다운(→직접수행), 스킬수정(→skill-builder), 옵시디언 볼트관리(→vault-mount).
vault_dependency: HARD
---

# Obsidian Flavored Markdown Skill

Create and edit valid Obsidian Flavored Markdown. Obsidian extends CommonMark and GFM with wikilinks, embeds, callouts, properties, comments, and other syntax. This skill covers only Obsidian-specific extensions -- standard Markdown (headings, bold, italic, lists, quotes, code blocks, tables) is assumed knowledge.


## Skill Boundaries

- **하는 것** — Obsidian Flavored Markdown 작성·편집.
- **안 하는 것** — 일반마크다운(→직접수행), 스킬수정(→skill-builder), 옵시디언 볼트관리(→vault-mount).

## When to Use

- 사용자가 "만들어줘", "작성해줘", "create", "write", "edit" 같은 표현으로 발동
- 옵시디언 노트 작성·편집시, 위키링크·콜아웃·임베드 문법이 필요할 때.
- **안 쓸 때** — 일반마크다운(→직접수행), 스킬수정(→skill-builder), 옵시디언 볼트관리(→vault-mount).


## Prerequisites

| # | 체크 | 미충족 시 |
|---|------|-----------|
| 1 | 대상·입력 명확 (스킬 발동 의도 확인) | 1줄 확인 후 진입 |
| 2 | references/ 폴더 접근 가능 | inline fallback |


## Workflow: Creating an Obsidian Note

1. **Add frontmatter** with properties (title, tags, aliases) at the top of the file. See [PROPERTIES.md](references/PROPERTIES.md) for all property types.
2. **Write content** using standard Markdown for structure, plus Obsidian-specific syntax below.
3. **Link related notes** using wikilinks (`[[Note]]`) for internal vault connections, or standard Markdown links for external URLs.
4. **Embed content** from other notes, images, or PDFs using the `![[embed]]` syntax. See [EMBEDS.md](references/EMBEDS.md) for all embed types.
5. **Add callouts** for highlighted information using `> [!type]` syntax. See [CALLOUTS.md](references/CALLOUTS.md) for all callout types.
6. **Verify** the note renders correctly in Obsidian's reading view.

> When choosing between wikilinks and Markdown links: use `[[wikilinks]]` for notes within the vault (Obsidian tracks renames automatically) and `[text](url)` for external URLs only.

## Internal Links (Wikilinks)

```markdown
[[Note Name]]                          Link to note
[[Note Name|Display Text]]             Custom display text
[[Note Name#Heading]]                  Link to heading
[[Note Name#^block-id]]                Link to block
[[#Heading in same note]]              Same-note heading link
```

Define a block ID by appending `^block-id` to any paragraph:

```markdown
This paragraph can be linked to. ^my-block-id
```

For lists and quotes, place the block ID on a separate line after the block:

```markdown
> A quote block

^quote-id
```

## Embeds

Prefix any wikilink with `!` to embed its content inline:

```markdown
![[Note Name]]                         Embed full note
![[Note Name#Heading]]                 Embed section
![[image.png]]                         Embed image
![[image.png|300]]                     Embed image with width
![[document.pdf#page=3]]               Embed PDF page
```

See [EMBEDS.md](references/EMBEDS.md) for audio, video, search embeds, and external images.

## Callouts

```markdown
> [!note]
> Basic callout.

> [!warning] Custom Title
> Callout with a custom title.

> [!faq]- Collapsed by default
> Foldable callout (- collapsed, + expanded).
```

Common types: `note`, `tip`, `warning`, `info`, `example`, `quote`, `bug`, `danger`, `success`, `failure`, `question`, `abstract`, `todo`.

See [CALLOUTS.md](references/CALLOUTS.md) for the full list with aliases, nesting, and custom CSS callouts.

## Properties (Frontmatter)

```yaml
---
title: My Note
date: 2024-01-15
tags:
  - project
  - active
aliases:
  - Alternative Name
cssclasses:
  - custom-class
---
```

Default properties: `tags` (searchable labels), `aliases` (alternative note names for link suggestions), `cssclasses` (CSS classes for styling).

See [PROPERTIES.md](references/PROPERTIES.md) for all property types, tag syntax rules, and advanced usage.

## Tags

```markdown
#tag                    Inline tag
#nested/tag             Nested tag with hierarchy
```

Tags can contain letters, numbers (not first character), underscores, hyphens, and forward slashes. Tags can also be defined in frontmatter under the `tags` property.

## Comments

```markdown
This is visible %%but this is hidden%% text.

%%
This entire block is hidden in reading view.
%%
```

## Obsidian-Specific Formatting

```markdown
==Highlighted text==                   Highlight syntax
```

## Math (LaTeX)

```markdown
Inline: $e^{i\pi} + 1 = 0$

Block:
$$
\frac{a}{b} = c
$$
```

## Diagrams (Mermaid)

````markdown
```mermaid
graph TD
    A[Start] --> B{Decision}
    B -->|Yes| C[Do this]
    B -->|No| D[Do that]
```
````

To link Mermaid nodes to Obsidian notes, add `class NodeName internal-link;`.

## Footnotes

```markdown
Text with a footnote[^1].

[^1]: Footnote content.

Inline footnote.^[This is inline.]
```

## Complete Example

````markdown
---
title: Project Alpha
date: 2024-01-15
tags:
  - project
  - active
status: in-progress
---

# Project Alpha

This project aims to [[improve workflow]] using modern techniques.

> [!important] Key Deadline
> The first milestone is due on ==January 30th==.

## Tasks

- [x] Initial planning
- [ ] Development phase
  - [ ] Backend implementation
  - [ ] Frontend design

## Notes

The algorithm uses $O(n \log n)$ sorting. See [[Algorithm Notes#Sorting]] for details.

![[Architecture Diagram.png|600]]

Reviewed in [[Meeting Notes 2024-01-10#Decisions]].
````

## References

조건부 로드: 요청 유형별 필수 reference 매핑: wikilink/embed 작업 → EMBEDS.md만. callout 작업 → CALLOUTS.md만. properties 작업 → PROPERTIES.md만. 복합 작업 → 해당 파일들만 로드. 3개 전부 로드는 '옵시디언 문법 전체 적용' 명시 요청 시만.

- [Obsidian Flavored Markdown](https://help.obsidian.md/obsidian-flavored-markdown)
- [Internal links](https://help.obsidian.md/links)
- [Embed files](https://help.obsidian.md/embeds)
- [Callouts](https://help.obsidian.md/callouts)
- [Properties](https://help.obsidian.md/properties)

## §INV NO_WORK_LABEL
산출물·대화 작업 라벨 ZERO. → `shaper-skill/references/no-work-label.md`


## Output Path

| 산출물 | 경로 |
|---|---|
| 주 산출물 | `mnt/outputs/obsidian-markdown_{topic}_{YYYY-MM-DD}.md` |
| 형식 | .md로, 옵시디언노트로. |
| 리서치 결과 (해당 시) | `{VAULT}/_skills research/obsidian-markdown/{YYYY-MM-DD}_{topic}.md` |


## Reference Index

| 파일 | 내용 | 언제 |
|---|---|---|
| `references/CALLOUTS.md` | CALLOUTS | 해당 단계 진입 시 |
| `references/EMBEDS.md` | EMBEDS | 해당 단계 진입 시 |
| `references/PROPERTIES.md` | PROPERTIES | 해당 단계 진입 시 |


## Next Phase

본 스킬 작업 후 자연스럽게 이어지는 흐름:

- 후속 작업 → `직접수행`
- 후속 작업 → `skill-builder`
- 후속 작업 → `vault-mount`


## Failure Modes (Gotchas)

| 함정 | 대응 |
|---|---|
| 트리거 오발동 | description NOT: 항목 확인 |
| 의존 파일 부재 | Prerequisites 표 재확인 |


## ❌ WRONG vs ✅ CORRECT

```
❌ WRONG: 트리거 단어만 보고 발동 — 본질·범위 확인 ✗ → 오발동·범위 이탈
✅ CORRECT: Skill Boundaries·When to Use 확인 후 발동 → 본질 작업만 수행
```
