# LoadWatch
Linux System LoadWatch

LoadWatch - A more lightweight version of Sys-Snap and only triggers when the load is higher than expected or wanted.

#### Version: 1.2.1

## INSTALLATION

1. Run the following command, as Root:

       mkdir -p ~/loadwatch; wget -O ~/loadwatch/loadwatch https://raw.githubusercontent.com/Hummdis/loadwatch/master/loadwatch && chmod +x ~/loadwatch/loadwatch

2. Install `facter`.  You can install it with the proper package manager for your distribution:
 - Arch Linux, Manjaro Linux: `sudo pacman -S facter`
 - Fedora: `sudo dnf install facter`
 - CentOS, RHEL: `sudo yum install epel-release && sudo yum install facter`
 - openSUSE: `sudo zypper install facter`

3. Create the following CRON entry in Root's crontab:

       */1 * * * * /root/loadwatch/loadwatch

4. You're done.  LoadWatch will run every minute (unless you change the CRON) and the defaults are to record the system state if the load is above the default of 50% of the CPU maximum ability.  If the server is a virtual machine (i.e. VPS), then the maximum load is 5 with a reported load of 2 or higher. This can be overridden, of course.  It then cleans up any old log files older than 14 days with each run to ensure no logs are kept longer than the defined retention period.

## CONFIGURATION

Defaults:
    THRESH: 50% of real CPU and 5 for virtual machines.
    RETEN: 14 days

Set the `THRESH` and `RETEN` variables at the top of the file to the desired numbers. Remember that the `THRESH` variable will be devided in 2, but rounded to the next highest whole number.

### Auto-Update

Default: true

New in version 1.2.0 is the auto-update feature. When a new version is published, it'll auto-update unless the `AUTO_UPDATE` variable is set to "false". Once set, it will only report in the checklog that an update is available.

If the Auto-Update option is disabled, a manual update may be performed by running `loadwatch update` on the command line to manually update the files.

## REVIEWING REPORTS

When it's time to review reports, the easiest way to see what the load was, and when, is to view the `checklog`.  There are timestamps with each check and what the load was at the time of that check. Once the threshold value has been reached it will trigger a dump of the information and that's where the individual `loadwatch_DATE.TIME.LOAD.txt` files come into play.  All dates that LoadWatch reports are in ISO 8601 date format of YYYY-MM-DD.

## Planned Changes

The plan is to add a configuration file that will be used to configure what data is contained in each dump and to enhance the overall performance of this tool.
