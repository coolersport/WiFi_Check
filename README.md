## WiFi_Check

### Purpose:
Script checks to see if WiFi has a network IP and if not
restart WiFi

Uses a lock file which prevents the script from running more
than one at a time.  If lockfile is old, it removes it

For more info:  
http://rpi.tnet.com/project/scripts/wifi_check

### Enhancements from Original Version

This forked version contains the following enhancements:

- change all `echo` statements to `logger` to avoid "(CRON) info (No MTA installed, discarding output)" error in crontab

### Others

For some reason, using `crontab -e` command doesn't work. You may need to edit `/etc/crontab` and insert the following line:

```bash
*/5 * * * * root /opt/wificheck >/dev/null 2>&1
```
