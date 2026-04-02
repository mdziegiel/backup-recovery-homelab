# 🧠 Backup & Recovery Architecture

## 🖼 Architecture Diagram
<img src="architecture.png" width="750"/>

---

## 📌 Overview
- Multi-layer backup strategy
- Local + replicated + offsite backups
- Separation of workloads and storage

---

## 🧱 Backup Layers

### Endpoint Backups
- UrBackup → QNAPNAS3

### Virtualization Backups
- Proxmox → PBS → QNAPNAS3

### NAS Replication
- QNAPNAS1 / NAS2 / NAS3
- HBS3 one-way sync

### Offsite Backup
- Backblaze (monthly critical data)

---

## 🔁 Backup Flow
- Daily: PBS + UrBackup
- Weekly: NAS workloads
- Monthly: Cloud backup

---

## 🧠 Infrastructure
- Intel NUC (Hyper-V)
  - PBS VM
  - UrBackup (Docker)
