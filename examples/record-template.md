# Record template

The person below is **fictional** and exists only to show the file shape. Do not copy these facts into a real file. In a real file, write only what the person confirmed, what a clinician confirmed, or what you advised, with a source label.

Write the real `profile.md`, `index.md`, and logs in English.

## Where files go

```text
hypertension-care-records/
├── index.md
└── Lin/
    ├── index.md
    ├── profile.md
    └── logs/
        └── YYYY-MM-DD.md
```

The folder name is the nickname the person asked to be called. Do not add a chart number. Do not record a legal name, national ID, home address, or phone number. If the person types them, leave them out of the file. In conversation, use the nickname.

## Source labels

Use one of these on every clinical statement:

- Patient-reported
- Clinician-confirmed
- AI-generated assessment
- Unknown or unverified

## Registry `hypertension-care-records/index.md`

```markdown
# Record index

| Nickname | Folder | Status | First record | Latest log |
|---|---|---|---|---|
| Lin | Lin/ | active | 2026-11-23 | 2026-11-23 |
```

## `Lin/index.md`

```markdown
# Lin

Fictional example. This is the name to use in conversation. There is no chart number.

## Latest status

- 2026-11-23: Home seated 146/88 and 142/86 mmHg before the morning dose. Both-ankle swelling in the evening. No chest pain or breathlessness. Source: patient-reported.
- Current clinician target: not recorded.
- Latest advice: keep amlodipine 5 mg; do not self-stop; same-week clinician visit for edema. Source: AI-generated assessment.

## Important events

| Date | Event | Source |
|---|---|---|
| 2026-11-23 | Profile opened under the nickname Lin. | Patient-reported |
```

## `Lin/profile.md`

```markdown
---
nickname: Lin
first_record_date: 2026-11-23
status: active
---

# Lin

Fictional example. Calculate age from `first_record_date` only as context. Do not invent a birthday. Address the person as Lin.

## 1. Basic profile

- Nickname: Lin
- Age: 68 years, stated on 2026-11-23. Source: patient-reported. Precision: year.
- Sex: female. Source: patient-reported.
- Marital status: lives with spouse. Source: patient-reported. Legal name not recorded.
- Occupation type: retired clerk. Source: patient-reported.
- Physical activity preferences: short walks to the market. Source: patient-reported.
- Lifestyle habits: eats out with family on weekends; no tobacco; alcohol not recorded.
- Living environment: apartment with an elevator. Source: patient-reported. Address not recorded.

## 2. Medical history

- Hypertension type: primary hypertension. Source: clinician-confirmed, as reported by the patient from a clinic booklet. The booklet was not seen.
- Hypertension duration: "about 8 years." Source: patient-reported.
- Diagnosis history: clinic booklet phrase not quoted beyond the type above. Source: patient-reported.
- Family history: mother had hypertension. Source: patient-reported.
- Comorbidities: none stated. Kidney disease, diabetes, and heart failure were asked and the answer was "the doctor has not told me I have those." Source: patient-reported. Not the same as a normal test.
- Previous cardiovascular events: not recorded.
- Allergies: not recorded.
- Surgical history: not recorded.

## 3. Current medication

### Amlodipine

- Medication name: product brand not recorded.
- Generic name: amlodipine. Source: patient-reported from the box.
- Dosage: 5 mg. Source: patient-reported from the box.
- Frequency: once daily. Source: patient-reported.
- Administration time: morning, before breakfast. Source: patient-reported.
- Start date: not recorded.
- Indication: hypertension. Source: patient-reported.
- Known side effects: both ankles swell by evening since summer. Source: patient-reported. Cause is not confirmed.
- Medication adherence: missed one morning last week and did not double the next dose. Source: patient-reported.

## 4. Current physical condition

- Current blood pressure: 2026-11-23 morning, seated, left arm, 146/88 then 142/86 mmHg. Source: patient-reported.
- Heart rate: 76 beats per minute on the same device. Source: patient-reported. Not an ECG.
- Body weight: not recorded.
- Height: not recorded.
- Sleep condition: usually asleep by 23:00, wakes once. Source: patient-reported.
- Physical activity: market walk on most days, about 15 minutes. Source: patient-reported.
- Current symptoms: both-ankle swelling. No chest pain, no breathlessness. Source: patient-reported.
- Edema status: both ankles, evening. Source: patient-reported.
- Current physiological condition: able to walk without a cane. Source: patient-reported.
- Recent health changes: swelling noticed this summer. Source: patient-reported.

## 5. Laboratory and examination results

- Kidney function: not recorded.
- Blood glucose: not recorded.
- Lipid profile: not recorded.
- Electrolytes: not recorded.
- Urine tests: not recorded.
- ECG: not recorded.
- Echocardiography: not recorded.
- Other relevant examinations: not recorded.

## 6. Blood pressure records

Detailed rows live in the logs. The latest pair is in section 4.

| Date | Time | Systolic | Diastolic | Heart rate | Position | Symptoms | Medication taken | Notes | Source |
|---|---|---|---|---|---|---|---|---|---|
| 2026-11-23 | before morning dose | 146 then 142 | 88 then 86 | 76 | seated, left arm | ankle swelling the evening before | previous day's dose taken | second reading after 1 minute | patient-reported |

## 7. Follow-up history

Full text is in `logs/`. The index holds the latest line.

## Profile changes

- 2026-11-23: Profile created from the first confirmed conversation. Fields not stated were left "not recorded."
```

## `logs/2026-11-23.md`

```markdown
# 2026-11-23

## Evening ankle swelling before a family meal

- Time: not stated.
- Patient questions: why both ankles swell, and how to eat at a wedding.
- Reported symptoms: both ankles swell by evening. No chest pain or breathlessness.
- Reported readings: seated 146/88 and 142/86 mmHg before the morning dose. Heart rate 76.
- Assessment: bilateral evening edema on amlodipine is a known drug effect but is not confirmed as the cause. Source: AI-generated assessment. One-sided sudden pain would be urgent. Source: AI-generated assessment.
- Recommendations: keep 5 mg; do not add or stop a dose; at the meal skip soup and pickles; walk 3 minutes each hour; repeat a seated pair tomorrow. Source: AI-generated assessment.
- Follow-up plan: ask the prescriber the same week about the swelling and whether labs are due. Bring 7 days of readings.
- Changes since previous visit: no earlier log.
- Still unverified: kidney function, clinician blood-pressure target, brand name, start date.
- Emergency advice given: no.
- Follows: none.
```

## Rules that are easy to break

- Do not fill an example value because the section looks empty.
- Do not store "primary hypertension" as clinician-confirmed unless the person is clearly reporting a clinician's diagnosis.
- Do not delete a medicine that was stopped. Move it to Profile changes with the stop date and who decided. If they stopped it themselves, write that.
- Same-day questions append under a new heading in the same log file.
