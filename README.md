# Log file cleaning script

This script deletes typical old log files, 
logrotate files, and similar log backups.

Please be certain you don't need
these log files before you run this.

This removes these kinds of log files from the `/var/log` directory:

File names that end with:

  * .bz2
  * .gz
  * .old
  * .bak
  * .backup
  * .log.[0-9]*
  * .[0-9]*.log

File names that match:

  * btmp.[0-9]*
  * dmesg.[0-9]*
  * mail.err.[0-9]*
  * syslog.[0-9]*
  * xferlog.[0-9]*
  * wtmp.[0-9]*

Any `atop` files. 

  * atop/atop_[0-9]*

Any Mac OSX Apple System Log files:

  * asl/*.asl
  * DiagnosticMessages/*.asl

## Implementation notes

This script aims to work even when a disk is full or commands are missing.
For example, this scripts starts by deleting files one name by one name,
rather than relying on more-sophisticated file globbing or using `find`.

This script source code aims to be descriptive and meaningful,
so a systems administrator can easily comment out lines as needed,
or add new lines easily without affecting any other lines.

If you are a developer who is creating a patch or pull request,
please keep this code pattern, rather than trying to introduce 
features such as more globbing, loops, non-POSIX commands, etc.

## Tracking

* Command: log-file-cleaning
* Version: 3.0.0
* Created: 2012-12-09
* Updated: 2016-08-27
* Contact: Joel Parker Henderson (joel@joelparkerhenderson.com)
* License: GPL
