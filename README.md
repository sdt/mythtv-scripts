## Miscellaneous scripts for my MythTV box

### checkshutdown

I use `checkshutdown --syslog` instead of `mythshutdown -c` to check that all's
ready for the backend to shut the machine down.

This script checks for various types of activity before giving the all clear:

    * active ssh sessions
    * recent apache activity (eg. mythweb)
    * sabnzbd downloading
    * mythshutdown --status

Inspired by [James FitzGibbon's mythcheckshutdown](https://github.com/jf647/mythcheckshutdown).  Thanks James!

I needed to modify my `/etc/logrotate.d/apache` file to make the apache logfile world-readable. This might not be the best solution.

### setwakeuptime

Called by mythbackend to set the ACPI wakeup time.

usage:

*MythShutdownNvramCmd* `sudo sh -c "/usr/local/bin/setwakeuptime $time`

Adapted from [this page on the MythTV wiki](http://www.mythtv.org/wiki/ACPI_Wakeup#Integrate_into_mythTV_2), with the addition of setting the BIOS clock before setting the wakeup alarm.
