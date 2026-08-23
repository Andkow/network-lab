# Lab environment

Dell XPS 8930 — i7-8700 (6C/12T), 32 GB DDR4, Ubuntu Server 24.04.
Hostname: lab. User: andko. On Tailscale.

## Storage — read carefully
- /dev/nvme?  466 GB Crucial P5 Plus — Ubuntu root. This is our disk.
- /dev/nvme?  238 GB Toshiba — WINDOWS. Never mount rw, never touch its ESP,
  never write to it. Dual-boot must keep working.
- /dev/sd?    2 TB Seagate, 3 NTFS partitions — existing data. Read-only only.

## Purpose
Network engineering lab, also career portfolio. containerlab (FRR, SR Linux,
cEOS), NetBox as source of truth, gNMI telemetry via gnmic into
Prometheus + Grafana, syslog sink. Later: RoCEv2/PFC/ECN on a dual-port
ConnectX-4.

## Hard rules
- Docker from Docker's official apt repo. NEVER snap — snap confinement
  breaks containerlab's netns manipulation.
- gnmic for telemetry collection, not Telegraf/SNMP.
- Everything as compose files committed to git. No ad-hoc docker run.
- Verify each step succeeded before starting the next. Stop on failure.
- Show me any command touching partitions, fstab, or bootloader before running.
