# Automating-Server-Backups-with-Bash-Scrip
🚀 Automating Server Backups with Bash! 🚀

As an IT professional, automating repetitive tasks is key to improving efficiency and minimizing human error. I recently wrote a simple yet powerful Bash script to automate server backups, which can save time and ensure your data is always backed up safely.

Here’s a breakdown of the script:

🔹 Source Directory: Define which directories to back up.
🔹 Destination: Store the backups in an organized way with timestamps.
🔹 Automation: Use tar to create compressed backups automatically.
🔹 Retention: Automatically remove old backups to manage storage efficiently.
🔹 Logging: Track successful or failed backups for easy monitoring.
#!/bin/bash

# Define backup source and destination
backup_src="/your_directory"
backup_dst="/backup"
backup_date=$(date +%Y%m%d%H%M%S)
backup_filename="backup_$backup_date.tar.gz"

# Create a directory for the backup
mkdir -p "$backup_dst/$backup_date"

# Archive and compress the source directory
tar -czf "$backup_dst/$backup_date/$backup_filename" "$backup_src"

# Verify backup success
if [ $? -eq 0 ]; then
    echo "Backup successful: $backup_filename"
else
    echo "Backup failed"
fi
