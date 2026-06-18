# User Model

## Description

Represents authenticated users of the platform.

## Fields

| Field | Type |
|---------|---------|
| id | bigint |
| uuid | uuid |
| name | string |
| email | string |
| password | string |
| role | enum |
| status | enum |
| last_login_at | timestamp |
| created_at | timestamp |
| updated_at | timestamp |

## Roles

- super_admin
- soc_admin
- instructor
- learner
- doctor

## Status

- active
- suspended
