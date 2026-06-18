# prerequisite

---

# PHASE 0 — Prerequisites (Must Be Clear First)

## 1️⃣ Oracle Physical Architecture

Understand:

- Database
- Instance
- SGA
- Background processes
- Datafiles
- Control files
- Redo log files
- Tablespaces

Focus on:

- What exists on disk vs memory
- What happens during startup/shutdown

---

## 2️⃣ Data Block Internals

Learn:

- Block structure (header, row directory, free space)
- SCN in block header
- Row format
- Undo blocks

Why important:

Recovery works at block level.

---

## 3️⃣ Redo and Undo (Critical)

You must clearly understand:

### Redo

- What is redo?
- Redo log buffer
- LGWR process
- Online redo logs
- Archived redo logs

Redo = used for recovery.

### Undo

- Undo segments
- Before images
- Read consistency
- Rollback

Undo ≠ redo.

---

## 4️⃣ SCN (System Change Number)

This is the backbone of recovery.

Understand:

- What is SCN?
- Commit SCN
- Checkpoint SCN
- Control file checkpoint
- How SCN guarantees consistency

If SCN is not clear, stop and master it.

---

# PHASE 1 — Crash vs Media Failure

Before backup, understand failures.

## 1️⃣ Instance Failure (Crash Recovery)

- Power failure
- Instance abort
- No file lost

Recovery uses:

- Online redo logs only

Automatic on startup.

---

## 2️⃣ Media Failure

- Datafile lost
- Disk corruption
- Control file loss

Now redo alone is not enough.

Now backup is required.

This is where backup becomes necessary.

---

# PHASE 2 — Recovery Concepts

## 1️⃣ Checkpoints

Understand:

- What happens during checkpoint?
- DBWR role
- Control file updated
- Redo log switch

Checkpoint ensures:

Datafiles are consistent up to an SCN.

---

## 2️⃣ Types of Recovery

### Instance Recovery

Automatic, no backup needed.

### Media Recovery

Requires:

- Backup
- Archived redo logs

---

## 3️⃣ Complete vs Incomplete Recovery

Complete:

Recover to latest SCN.

Incomplete:

Recover to:

- Specific time
- SCN
- Sequence number

---

# PHASE 3 — Backup Types

Now backup starts making sense.

## 1️⃣ Physical Backups

- Cold backup (consistent)
- Hot backup (inconsistent, needs redo)
- RMAN backups
- Full
- Incremental (Level 0, Level 1)

Understand:

Why hot backup requires ARCHIVELOG mode.

---

## 2️⃣ Logical Backups

- Data Pump
- Export/Import

Use cases:

- Migration
- Object restore

Not full disaster recovery.

---

# PHASE 4 — ARCHIVELOG Mode

Now learn:

- NOARCHIVELOG
- ARCHIVELOG
- Switching modes
- ARCn process
- Archive destinations

Key insight:

Without archived redo logs → no media recovery.

---

# PHASE 5 — RMAN (Core Production Topic)

Learn RMAN in this order:

1. RMAN architecture
2. Backup sets vs image copies
3. Full backup
4. Incremental backup
5. Restore
6. Recover
7. Block recovery
8. Control file recovery
9. SPFILE recovery

---

# PHASE 6 — Advanced Topics

- Flashback Database
- Flashback Table
- Restore points
- Data Guard
- Block change tracking
- Backup optimization
- Retention policies

---

# Suggested Study Order (Exact Sequence)

1. Physical architecture
2. Redo + Undo
3. SCN
4. Checkpoint
5. Instance recovery
6. Media recovery
7. ARCHIVELOG mode
8. Backup types
9. RMAN
10. Flashback

Do not jump ahead.

---

# Why You’re Confused

Because backup is not an isolated topic.

It is built on:

Redo + SCN + Checkpoint + File structure.

If those are weak, backup feels abstract.

---

# How to Study Practically

If possible:

1. Create test database.
2. Put it in NOARCHIVELOG.
3. Take cold backup.
4. Delete a datafile.
5. Try recovery.

Then:

1. Enable ARCHIVELOG.
2. Take hot backup.
3. Insert rows.
4. Delete datafile.
5. Recover.

Experience removes confusion.

---