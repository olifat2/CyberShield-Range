# Medical Record Model

## Description

Represents medical records linked to patients.

## Fields

| Field | Type |
|---------|---------|
| id | bigint |
| uuid | uuid |
| patient_id | foreign key |
| created_by | foreign key |
| title | string |
| diagnosis | text |
| treatment | text |
| notes | longText |
| severity | enum |
| status | enum |
| created_at | timestamp |
| updated_at | timestamp |

## Severity

- low
- medium
- high
- critical

## Status

- open
- in_progress
- closed
