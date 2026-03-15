Backup Strategy

This document describes the backup strategy planned for the home server.

The goal is to ensure that important data is not lost in case of disk failure, accidental deletion, or system issues.

---

Backup Principle

The server will follow a simplified version of the 3-2-1 backup rule.

3 copies of important data
2 different storage locations
1 optional external backup

---

Primary Storage

Main data will be stored on the server HDD.

Example storage location:

/storage

Contents include:

- Nextcloud files
- Photos
- Media files
- Documents

---

Local Backup

A backup copy will be stored inside a separate backup directory.

Example structure:

/storage/backups

Data from important folders will be copied here regularly.

Backup example:

/storage/nextcloud → /storage/backups/nextcloud

---

Backup Method

Backups will be performed using the rsync tool.

Example command:

rsync -av /storage/nextcloud /storage/backups/

rsync copies only changed files, making backups faster and efficient.

---

Automated Backups

Backups can be scheduled using cron jobs.

Example schedule:

Daily backup at 2:00 AM.

This ensures that important data always has a recent backup copy.

---

External Backup (Optional)

For additional safety, an external hard drive can be used.

Example:

Server HDD → main data
External HDD → backup copy

This protects data even if the main disk fails.

---

Data Recovery

If data is lost, files can be restored from the backup folder.

Example restore process:

/storage/backups → /storage

This allows quick recovery of deleted or corrupted files.

---

Summary

The backup strategy ensures that important data stored on the home server is protected and recoverable in case of unexpected failures.
