# Crime Investigation Database

1. Create a CRIME_SCENE table with:
    - SCENE_ID
    - LOCATION
    - INCIDENT_DATE
    - OFFICER_IN_CHARGE
    - CASE_STATUS
2. CASE_STATUS allowed values: OPEN, CLOSED, UNDER_INVESTIGATION.
3. Create an EVIDENCE table:
    - EVIDENCE_ID
    - SCENE_ID
    - DESCRIPTION
    - TYPE
    - COLLECTED_BY
    - COLLECTED_AT
4. Foreign key on SCENE_ID referencing CRIME_SCENE.
5. Add a CHECK constraint ensuring COLLECTED AT≥ INCIDENT_DATE.
6. Create a SUSPECT table: 
    - SUSPECT_ID
    - NAME
    - DOB
    - ADDRESS
    - RISK_LEVEL
7. RISK_LEVEL : ‘LOW’, ‘MEDIUM’,’HIGH’
8. Create a CASE_ASSIGNMENT table:
    - ASSIGNMENT_ID
    - OFFICER_NAME
    - SCENE_ID
    - ASSIGNED_DATE
9. Foreign key on SCENE_ID.
10. Add a CRIME_TYPE table and connect it with CRIME_SCENE via a foreign key.
11. Create a FORENSIC_LAB table:
    - LAB_ID
    - LAB_NAME
    - LOCATION
    - CERTIFIED_TILL
12. Add a CHECK ensuring certification validity date > current date.
13. Alter EVIDENCE to include LAB_ID with FK to FORENSIC_LAB.
14. Rename column DESCRIPTION in EVIDENCE to EVIDENCE_DETAILS.
15. Add a new table CHAIN_OF_CUSTODY:
    - RECORD_ID
    - EVIDENCE_ID
    - FROM_PERSON
    - TO_PERSON
    - TRANSFER_TIME
    - 
16. FK to EVIDENCE.
17. Add NOT NULL constraints on all ID columns retroactively.
18. Drop the RISK_LEVEL column and reintroduce it as a reference to a new table RISK_LEVELS.