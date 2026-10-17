# Laboratory 09 – Understanding Cloud Automation

**Student:** Kylle Zyrence F. Mariano  
**Course:** CCM101 – Cloud Computing  
**Mission:** Cloud Automation Engineer

## 1. Bash Script

A Bash script is a file that contains Linux commands arranged to perform specific tasks automatically. Instead of entering commands individually every time, a user can save them in a script and execute them as a single process. This is useful for managing servers, organizing files, and creating regular backups.

The `#!/bin/bash` statement at the beginning of the script is known as a shebang. It identifies Bash as the interpreter responsible for executing the script when it is launched directly.

## 2. Variables

Variables are names assigned to values that a Bash script can use during execution. They make scripts more flexible by allowing information such as folder locations, file names, and timestamps to be stored and referenced whenever needed.

For example, a variable named `BACKUP_DIR` can contain the location of a backup folder. If the destination changes, the administrator only needs to modify the variable instead of updating several commands throughout the script.

## 3. Cron Job

A Cron job is a Linux scheduling mechanism that automatically runs a command or script according to a specified time interval. It uses a crontab file to define when a task should execute, such as every hour, every day, or on selected days of the week.

Cron is useful in cloud environments because important maintenance activities can be performed consistently without requiring someone to manually start them. Scheduled backups, cleanup procedures, and system monitoring are common examples of its applications.

## Conclusion

Learning about Bash scripts, variables, and Cron jobs provides a foundation for automating Linux administration tasks. These tools help reduce repetitive work, improve consistency, and support more efficient cloud operations.

## References

- GNU Project. (n.d.). *Bash Reference Manual*. https://www.gnu.org/software/bash/manual/
- GNU Project. (n.d.). *Bash Variables*. https://www.gnu.org/software/bash/manual/html_node/Shell-Variables.html
- Ubuntu. (n.d.). *CronHowto*. https://help.ubuntu.com/community/CronHowto
