# Laboratory 09 – Backup Script and Cron Scheduling Guide

**Student:** Kylle Zyrence Mariano  
**Course:** CCM101 – Cloud Computing  
**Mission:** The Cloud Automation Engineer  
**Environment:** KillerCoda Ubuntu Linux

## Overview

This document explains how a Bash script was created and tested to generate compressed backups of application data. It also describes the Linux commands used to manage script permissions and configure a daily backup schedule using Cron.

## 1. Preparing the Sample Data

The application directory and sample file were created using the following commands:

```bash
mkdir -p app-data
echo "This is critical client data." > app-data/data.txt
cat app-data/data.txt
```

The `cat` command displayed the sample text, confirming that the file was created successfully.

## 2. Creating the Bash Backup Script

The script was created in the Nano text editor:

```bash
nano backup.sh
```

The following script was used:

```bash
#!/bin/bash

SOURCE_DIR="/root/app-data"
BACKUP_DIR="/root/backups"
TIMESTAMP=$(date +"%Y%m%d_%H%M%S")
BACKUP_FILE="$BACKUP_DIR/kylle-backup-$TIMESTAMP.tar.gz"

echo "Starting automated backup..."
mkdir -p "$BACKUP_DIR"

if tar -czf "$BACKUP_FILE" -C "$(dirname "$SOURCE_DIR")" "$(basename "$SOURCE_DIR")"; then
    echo "Backup completed successfully: $BACKUP_FILE"
else
    echo "Backup failed."
    exit 1
fi
```

### Script Explanation

- `#!/bin/bash` identifies the Bash interpreter.
- `SOURCE_DIR` stores the location of the application data.
- `BACKUP_DIR` specifies the folder where compressed backups are saved.
- `TIMESTAMP` generates a date-and-time value for the filename.
- `BACKUP_FILE` defines the full path of the generated backup archive.
- `mkdir -p` creates the destination folder when necessary.
- `tar -czf` compresses the source folder into a `.tar.gz` file.
- The `if` statement checks whether the compression command succeeded.
- `echo` displays a success or failure message.

## 3. Testing File Permissions

The script was initially executed using:

```bash
./backup.sh
```

The terminal returned a `Permission denied` error because the script did not yet have executable permission.

The following command was then used:

```bash
chmod +x backup.sh
```

The `chmod +x` command grants executable permission, allowing the Bash script to be run directly.

## 4. Running and Verifying the Backup

After updating the permissions, the following commands were executed:

```bash
./backup.sh
ls -lh /root/backups/
```

The script successfully generated compressed backup archives.

The directory listing confirmed two files:

- `kylle-backup-20261017_034914.tar.gz`
- `kylle-backup-20261017_035001.tar.gz`

Both files were approximately 177 bytes in size.

### Screenshot Evidence

![Backup Script Execution](screenshots/script-execution.png)

## 5. Configuring a Cron Job

The existing Cron schedule was checked using:

```bash
crontab -l
```

Initially, the terminal displayed `no crontab for root`, indicating that no scheduled tasks had been configured for the root user.

The Cron editor was opened using:

```bash
env EDITOR=nano crontab -e
```

The following entry was added:

```cron
0 2 * * * /root/backup.sh
```

### Explanation of the Cron Expression

| Field | Value | Meaning |
|---|---|---|
| Minute | `0` | At minute zero |
| Hour | `2` | At 2:00 AM |
| Day of Month | `*` | Every day of the month |
| Month | `*` | Every month |
| Day of Week | `*` | Every day of the week |

The schedule was verified using:

```bash
crontab -l
```

The output confirmed that the daily 2:00 AM Cron entry was saved. This verifies the configuration, although the scheduled execution itself was not observed.

### Screenshot Evidence

![Cron Schedule](screenshots/cron-schedule.png)

## 6. Importance of Automation

Bash scripts and Cron jobs help Linux administrators perform routine tasks without repeatedly entering commands. Automated backups can improve consistency and reduce manual work, although administrators should still monitor execution results and periodically test whether backup archives can be restored.

## Conclusion

This laboratory demonstrated the practical use of Bash scripting, Linux permissions, file compression, and Cron scheduling. The backup script was tested successfully, and a recurring backup schedule was configured for daily execution.
