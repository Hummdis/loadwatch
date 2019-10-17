# loadwatch
Linux System Load Watch

LoadWatch - A more lightweight version of Sys-Snap and only triggers when the load is higher than expected or wanted.

#### Version: 1.1.2

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

4. You're done.  It'll run every minute and the defaults are to record the system state if the load is above the default of 50% of the CPU maximum ability.  If the server is a virtual machine (i.e. VPS), then the maximum load is 16 with a reported load of 8 or higher. This can be overridden, of course.  It then cleans up any old log files older than 14 days.

## CONFIGURATION

Set the `THRESH` and `RETEN` variables at the top of the file to the desired numbers.
