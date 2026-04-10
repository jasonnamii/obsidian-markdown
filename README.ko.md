# Obsidian 마크다운 스킬

> 🇺🇸 [English README](./README.md)

**Obsidian 마크다운 레퍼런스 및 생성 도구: 위키링크, 임베드, 콜아웃, 속성, 고급 신택스**

## 사전 요구사항

- **Obsidian Vault** — 활성화된 Obsidian vault (로컬 또는 클라우드 동기화)
- **Obsidian MCP Server** — `search_notes`, `read_note`, `get_frontmatter`에 대한 읽기 권한
- **Claude Cowork 또는 Claude Code** 환경

## 목적

obsidian-markdown은 Obsidian 신택스에 대한 레퍼런스 및 실행 엔진을 제공합니다. 위키링크, 임베드, 콜아웃, frontmatter 속성, 블록 참조, 주석, 태그를 올바르게 포맷팅하여 vault 전체에서 일관성을 유지합니다.

## 사용 시점 및 방법

Obsidian vault 내에서 노트를 작성, 편집, 리팩토링할 때 배치하세요. 신택스 상기용 레퍼런스로 사용하거나 기존 마크다운에 Obsidian 기능을 체계적으로 추가할 때 실행 도구로 사용합니다.

## 사용 예시

| 상황 | 프롬프트 | 결과 |
|---|---|---|
| 모든 기능이 포함된 새 노트 | `"Create note on Strategic Planning with wikilinks, properties, callouts"` | Frontmatter→위키링크→콜아웃→블록 참조→신택스 검증 |
| 외부 링크 변환 | `"Refactor: convert links to wikilinks, add properties, create callout summaries"` | 링크 대상→위키링크→frontmatter 속성→콜아웃 감싸기 |
| 연결된 지식 기반 | `"Add embeds and bidirectional links throughout project folder"` | 계층 구조→위키링크→임베드→속성→블록 참조 |

## 핵심 기능

- 위키링크: `[[Note Name]]` 선택적 별칭 포함; 자동 역링크 생성
- 임베드: `![[Note Name]]` 또는 `![[Note Name#^block-id]]`; 실시간 업데이트
- 콜아웃: 12가지 타입 (note, tip, important, warning 등)
- Frontmatter 속성: 정렬, 필터링, 자동화를 위한 YAML 메타데이터
- 블록 참조: 정확한 내부 인용을 위한 `^block-id`
- 주석: `%% comment %%` 미리보기에서 숨겨짐
- 올바른 포맷팅을 위한 신택스 검증


## 연관 스킬

- **[html-div-style](https://github.com/jasonnamii/html-div-style)** — Obsidian 호환성 유지 시각 스타일링
- **[deliverable-engine](https://github.com/jasonnamii/deliverable-engine)** — Obsidian 신택스로 복잡한 노트 구조화

## 설치

```bash
git clone https://github.com/jasonnamii/obsidian-markdown.git ~/.claude/skills/obsidian-markdown
```

## 업데이트

```bash
cd ~/.claude/skills/obsidian-markdown && git pull
```

`~/.claude/skills/`에 배치된 스킬은 Claude Code 및 Cowork 세션에서 자동으로 사용할 수 있습니다.

## Cowork 스킬 생태계

25개 이상의 커스텀 스킬 중 하나입니다. 전체 카탈로그: [github.com/jasonnamii/cowork-skills](https://github.com/jasonnamii/cowork-skills)

## 라이선스

MIT 라이선스 — 자유롭게 사용, 수정, 공유하세요.
