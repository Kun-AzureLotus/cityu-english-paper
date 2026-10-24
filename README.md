# CityUHK English Paper Editor

A reusable agent skill for editing an existing English academic draft. It reduces formulaic expression while preserving the student's argument, evidence, citations, uncertainty, and writing voice.

面向香港城市大学学生的英文论文编辑技能。用于修改已有草稿，减少套话、重复和机械表达，同时保护原意、数据、引用和学术限定。默认用中文说明修改，论文正文保持英文。

## What it does

- Offers review, light editing, authorized restructuring, and review of supplied Turnitin highlights.
- Uses an optional authentic writing sample to preserve the author's register and preferences.
- Applies different editorial decisions to abstracts, introductions, literature reviews, methods, results, discussions, and conclusions.
- Checks whether edits change quantities, attribution, causality, negation, conditions, or uncertainty.
- Flags missing evidence instead of inventing references, findings, or personal experience.

## Scope and limitations

This is an editorial workflow, not an AI detector. It does not guarantee a lower Turnitin score, diagnose authorship, or contain a hidden CityU-specific detection formula. It does not draft a complete paper from scratch, fabricate a writing history, or manufacture a declaration that no AI was used.

Course and assessment instructions determine what assistance is permitted. No institutional endorsement or university-wide permission is implied. Public policy sources and verification limits are recorded in [CityUHK context](references/cityu-context.md).

## Install

With a compatible Skills CLI:

```sh
npx skills add https://github.com/Kun-AzureLotus/cityu-english-paper --skill cityu-english-paper
```

This CLI installation command has not been tested for this repository. Manual installation is also available:

Download or clone this repository. Copy its directory, containing `SKILL.md`, `agents/`, and `references/`, into your agent's skills directory under the name `cityu-english-paper`.

For Codex, the usual user-level destination is `~/.codex/skills/cityu-english-paper/`. Restart or reload skills if the host requires it. Other agents must support the `SKILL.md` format; their discovery and invocation behavior may differ.

No scripts, external scoring APIs, or package dependencies are required by this skill.

## Use

```text
使用 $cityu-english-paper 润色以下英文论文草稿。
先按轻度编辑处理，保留观点、数据、引用和我的风格。
需要补充的证据请单独列出，不要编造。

[Existing English draft]
```

Optional context: assignment brief, rubric, word limit, citation style, course AI-use instructions, and a short authentic sample of comparable writing. Provide a report only if you want its specific highlights reviewed; an AI report and a Similarity Report are different.

For feedback without rewriting:

```text
Use $cityu-english-paper in review mode. Identify unclear reasoning,
formulaic phrasing, and unsupported claims. Do not rewrite the paper.
```

## Example

Invented teaching input:

> It is important to note that the survey included 84 respondents from two firms. These findings may suggest an association between training and reported confidence.

Possible revision:

> The survey included 84 respondents from two firms. The findings suggest a possible association between training and reported confidence.

The revision removes empty framing while preserving sample size, scope, self-reported measurement, and uncertainty. It makes no claim about a detector score.

## Files

- [SKILL.md](SKILL.md): reusable instructions.
- [agents/openai.yaml](agents/openai.yaml): interface metadata.
- [Academic editing](references/academic-editing.md): section-specific decisions and semantic checks.
- [CityUHK context](references/cityu-context.md): official sources and verification limits.
- [Design sources](references/design-sources.md): selected public skills and excluded approaches.

## Validation status

Frontmatter structure and bundled reference paths were checked locally. The upstream skill validator could not run because PyYAML was unavailable; dependency installation was blocked by network name resolution. No live Turnitin test, representative writing benchmark, or institutional approval has been performed.

Public context was checked on 24 October 2026. Policies, course instructions, and detector behavior may change.
