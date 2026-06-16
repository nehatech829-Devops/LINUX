## **Cron Jobs in Linux**



Overview



A Cron Job is a time-based task scheduler in Linux used to automate repetitive tasks such as backups, log cleanup, system updates, and script execution.



The cron service runs in the background and executes commands or scripts at scheduled times.







##### **What is Cron?**



Cron is a daemon that executes scheduled commands according to entries stored in a crontab (cron table).



\### Check Cron Service Status



sudo systemctl status cron





Start Cron Service:



sudo systemctl start cron





Enable Cron at Boot:



sudo systemctl enable cron



\## Crontab Commands



\### View Current Cron Jobs





crontab -l





\### Edit Cron Jobs





crontab -e





\### Remove All Cron Jobs





crontab -r





\### List Another User's Cron Jobs





sudo crontab -u username -l





##### **Cron Job Syntax**



\* \* \* \* \* command\_to\_execute

¦ ¦ ¦ ¦ ¦

¦ ¦ ¦ ¦ +-- Day of Week (0-7)

¦ ¦ ¦ +---- Month (1-12)

¦ ¦ +------ Day of Month (1-31)

¦ +-------- Hour (0-23)

+---------- Minute (0-59)



##### **Common Cron Job Examples**



\### Run Every Minute



\* \* \* \* \* /home/user/script.sh





\### Run Every Day at 2:00 AM



0 2 \* \* \* /home/user/backup.sh





\### Run Every Sunday at 5:00 PM



0 17 \* \* 0 /home/user/report.sh



\### Run Every 5 Minutes



\*/5 \* \* \* \* /home/user/script.sh





\### Run Every Hour



0 \* \* \* \* /home/user/script.sh



\### Run on the First Day of Every Month



0 0 1 \* \* /home/user/monthly\_backup.sh



\## Redirect Output to Log File



0 2 \* \* \* /home/user/backup.sh >> /var/log/backup.log 2>\&1



Explanation:



\* `>>` Appends output to log file

\* `2>\&1` Redirects errors to the same log file





##### **Special Strings**



\### Run at System Startup



@reboot /home/user/startup.sh



\### Run Once Every Hour



@hourly /home/user/script.sh



\### Run Once Every Day



@daily /home/user/script.sh



\### Run Once Every Week



@weekly /home/user/script.sh





\### Run Once Every Month



@monthly /home/user/script.sh





\### Run Once Every Year



@yearly /home/user/script.sh



##### **Practical Examples**



\### Automatic Backup



0 1 \* \* \* tar -czf /backup/home\_backup.tar.gz /home/user



\### Delete Temporary Files Daily



0 3 \* \* \* rm -rf /tmp/\*





\### Log System Information Every Hour



0 \* \* \* \* df -h >> /home/user/disk\_usage.log



##### **Verify Cron Job Execution**



Check system logs:



grep CRON /var/log/syslog





Or:



sudo journalctl -u cron



##### **Best Practices**



\* Use absolute paths in cron jobs.

\* Redirect output to log files.

\* Test scripts manually before scheduling.

\* Keep cron entries organized and documented.

\* Regularly review scheduled tasks.



##### **Conclusion**



Cron Jobs are one of the most powerful Linux automation tools. They help automate repetitive administrative tasks, improve efficiency, and reduce manual effort by executing commands and scripts on a predefined schedule.



