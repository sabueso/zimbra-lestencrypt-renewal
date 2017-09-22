Zimbra-letsencrypt-renewal
==========================


One simply script (and improvable) to renew automatically your Let's Encrypt Certificate, unattendly (without rebooting unnecesarily)

### Usage

Only edit vars to adjust to your system. The script use /tmp to add text safely and copy needed files to zimbra directory, and run all necesesarily commands.

### Cron

Edit crontab as following:


```sh
00 2	* * *	root	certbot renew --pre-hook "su - zimbra -c 'zmcontrol stop'" --post-hook  "sh /root/zimbra-letsencrypt-renewal/renew_script.sh; su - zimbra -c 'zmcontrol start'"
```
This will try to renew your cert 2 AM. Reboot will be done only when renewal is feaceble.


Improvements are welcome! ;)

---
Ramiro Magallanes <sabueso@sabueso.org>

