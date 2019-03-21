# zfs-auto-snapshot Ansible role

[![CircleCI](https://circleci.com/gh/angristan/ansible-zfs-auto-snapshot.svg?style=svg)](https://circleci.com/gh/angristan/ansible-zfs-auto-snapshot)

This is an ansible role for [zfsonlinux/zfs-auto-snapshot](https://github.com/zfsonlinux/zfs-auto-snapshot), the ZFS Automatic Snapshot Service for Linux.

It will copy the zfs-auto-snapshot script and man(8).

5 cron are available:

- frequent (every 15 minutes)
- hourly
- daily
- weekly
- monthly

Each cron has its own retention time.

You can enable/disable crons and tune their retention periods using variables. See `defaults/main.yml`.

## Example playbook

Example:

```yaml
---

- hosts: zfsbox
  roles: zfs-auto-snapshot
  vars:
    zfs_auto_snapshot_monthly_disabled: true
    zfs_auto_snapshot_hourly_keep: 48
```
