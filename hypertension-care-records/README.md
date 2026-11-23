# Local patient records

This directory holds hypertension records for the current workspace. Each person has one folder, named with the nickname they asked to be called. There is no chart number.

Only this README is meant to be tracked in Git. Profiles, the registry `index.md`, each nickname folder, and everything under `logs/` are ignored. Do not force-add them.

Real records must not contain a legal name, national ID number, street address, or phone number. City, the current hospital or clinic, and the doctor's stated advice may be recorded after the person confirms them. If a nickname folder already exists and it is unclear whether this is the same person, ask before writing.

The fictional shape lives in `examples/record-template.md`.

Layout:

```text
hypertension-care-records/
├── README.md          tracked, no patient data
├── index.md           local registry, not tracked
└── <nickname>/
    ├── index.md
    ├── profile.md
    └── logs/
```

The agent writes profiles and logs in English and labels each fact as patient-reported, clinician-confirmed, AI-generated assessment, or unknown or unverified. In conversation, use the nickname.
