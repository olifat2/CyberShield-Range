# Relationships

## User

User
└── hasMany MedicalRecord

## Patient

Patient
└── hasMany MedicalRecord

## MedicalRecord

MedicalRecord
├── belongsTo User
└── belongsTo Patient
