Update-MOTD
===========

This repository provides a basic bash interface to dynamically update the
`/etc/motd` file.

## Usage

The `update-motd` script iterates through every script in `/etc/update-motd.d/`
and directs the output to `/etc/motd`. Ordering is controlled via the script
number (e.g. `00-header`, `10-sysinfo`, etc.) You may alter the scripts or change
the order to show as much or as little information as possible. 

The `motd-upd-count` script is referenced by the `20-updates` script, and
generates a count of all pending updates that have not been installed. 

The _systemd_ unitfiles run `update-motd` at 1 minute after boot, and every
30 minutes after. 

## Custom Configuration

Add or alter the scripts in `/etc/update-motd.d` to suit your needs. Any output
produced by these scripts is used as part of the motd. Pay attention to
the numbering to ensure proper ordering.


