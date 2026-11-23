# hypertension-care-skill

**English** | [简体中文](README.zh-CN.md)

Agent skill for long-term, practical support of adults living with hypertension, especially middle-aged and older adults who have other illnesses, several medicines, or less ability to move.

```text
Use this skill when the person asks about blood pressure, antihypertensive medicines, home readings, food, activity, or follow-up.
```

This skill does **not** diagnose, prescribe, stop, or change a dose, and it does **not** replace a clinician, a test, or emergency services.

```bash
npx skills add sendsoon/hypertension-care-skill
```

## What this skill does

`hypertension-care-skill` is a workflow for coding agents (Cursor, Claude Code, Codex, and others that load `SKILL.md`). When a person describes a real situation, the agent:

1. Matches one nickname, or asks before mixing two people
2. Reads that person's local profile, index, and latest log
3. Checks for emergency symptoms before giving ordinary advice
4. Separates guideline recommendations, clinical knowledge, a personal suggestion, and unknown facts
5. Gives a step that can be done at the next meal, the next measurement, or the next clinician visit
6. Asks one missing question instead of a long form
7. After confirmation, updates the English record and appends a log without deleting history

Population blood-pressure targets differ across WHO, ISH, ESC, AHA/ACC, the 2024 Chinese guideline, and KDIGO. The skill names the difference. It does not invent a target for the person.

## Records

Records live in `hypertension-care-records/<nickname>/` in the **current workspace**. The folder name is the nickname the person chose. Profiles and logs are English. Each fact is marked patient-reported, clinician-confirmed, AI-generated assessment, or unknown or unverified.

The folder is gitignored except for this directory's README. The repository does not contain a real medical history. A new workspace has no sample patient. The fictional shape is [examples/record-template.md](examples/record-template.md).

Do not store a legal name, national ID number, street address, or phone number. The record does keep the city, the hospital or clinic they already use, and what the doctor told them to do.

When a non-urgent visit is needed, the agent searches public information for hospitals in that city and names the source. It does not invent a ranking. An emergency still goes to the nearest emergency department.

## When to use it

Use it for hypertension, home blood pressure, understanding a medicine already prescribed, salt and meals, walking and other activity, sleep, travel, work, and living with heart, kidney, or metabolic disease beside high blood pressure.

Do not use it to choose a drug or a dose, to clear a person for intense exercise, to manage a child as if they were an adult, or to delay emergency care. In mainland China the public medical emergency number is 120. Elsewhere, use the local emergency number.

## Install

```bash
npx skills add sendsoon/hypertension-care-skill
```

Or clone the repository and copy `SKILL.md`, `references/`, and `examples/` into your agent's skills directory. Keep those relative paths.

The [skills.sh](https://skills.sh/) catalog page updates after install telemetry arrives.

`.agents/` and `.claude/` in this repository are local pointers for agents that look in those folders. They are gitignored and are not part of the install.

## Update the skill

If you installed with the Skills CLI, pull the latest `SKILL.md` from GitHub:

```bash
npx skills check
npx skills update hypertension-care-skill
```

`check` only reports whether a newer hash exists. `update` reinstalls this skill into the same agents as before. To refresh every installed skill:

```bash
npx skills update
```

Skip the confirm prompt with `-y`:

```bash
npx skills update hypertension-care-skill -y
```

Re-running the install command also refreshes the files:

```bash
npx skills add sendsoon/hypertension-care-skill
```

If you copied files by hand, `git pull` this repository and copy `SKILL.md`, `references/`, and `examples/` over the previous copy.

## Usage

```text
I am 70. This morning's readings were 168/92 and 164/90 before the pill. I take half a tablet but I am not sure of the name. What should I do today?
My ankles swell every evening on amlodipine. Can I stop it before Saturday's dinner?
I felt dizzy when I stood up. My seated reading was 102/64.
```

If the medicine name or strength is missing, the agent asks for the box. It does not guess.

## Output

Emergency symptoms: the reply is the emergency step.

A simple question: a short answer, not all seven sections.

A concrete problem, in Chinese:

1. 问题判断
2. 原因分析
3. 风险评估
4. 具体建议
5. 日常注意事项
6. 就医及检查建议
7. 后续跟踪

A fictional example is in [examples/output-template.md](examples/output-template.md).

## Project layout

```text
hypertension-care-skill/
├── SKILL.md
├── skills.sh.json
├── skills-lock.json
├── README.md
├── README.zh-CN.md
├── LICENSE
├── references/
│   ├── hypertension-guidelines.md
│   ├── medication-reference.md
│   ├── complications.md
│   ├── lifestyle-management.md
│   ├── elderly-care.md
│   ├── emergency-warning.md
│   ├── follow-up-strategies.md
│   └── local-care.md
├── examples/
│   ├── output-template.md
│   └── record-template.md
└── hypertension-care-records/    # local, gitignored except README.md
```

| File | Role |
|---|---|
| `SKILL.md` | What the agent executes. YAML `name` / `description` control discovery. |
| `references/` | Guidelines, medicines, comorbidities, daily life, older age, emergencies, follow-up. Open only the file the question needs. |
| `examples/` | Reply shape and a fictional record. Not real patients. |
| `hypertension-care-records/` | One folder per nickname. |
| `skills.sh.json` | Grouping label for a skills.sh repo page, if this repository is published. It does not change clinical behavior. |
| `skills-lock.json` | Local lock only. No upstream hash, because this copy is not a published release. |

## Medical sources

Reference files cite WHO 2021, ISH 2020, ESC 2024, the 2025 AHA/ACC multisociety high blood pressure guideline, the 2024 Chinese hypertension guideline, and KDIGO 2021 for blood pressure in chronic kidney disease, plus WHO sodium and physical-activity documents and the NHLBI DASH page. They were checked on 2026-11-23. They are not a substitute for the current official PDF, and they do not cite papers that were not identified.

## License

[MIT](LICENSE)
