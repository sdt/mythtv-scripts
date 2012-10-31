## Miscellaneous scripts for my MythTV box

### checkshutdown

I use `checkshutdown --syslog` instead of `mythshutdown -c` to check that all's
ready for the backend to shut the machine down.

This script checks for various types of activity before giving the all clear:
    * active ssh sessions
    * recent apache activity (eg. mythweb)
    * sabnzbd downloading
    * mythshutdown --status

