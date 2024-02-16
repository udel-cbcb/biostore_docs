# Archiving Data from User Shares to Tape SOP
 
**Step 1: Create the Archive Directory**

Within each group's shared folder (home directory), create an `archive` directory.

**Step 2: Organize Files for Archiving**

Inside the "archive" directory, create a sub-directory named `xxxx` and place the files you wish to archive in this sub-directory.

**Step 3: Prepare for Archiving**

Once all the files are inside `xxxx` and ready for backup, rename the directory to `xxxx.ready`.

**Step 4: Automate Directory Renaming and Protection**

Admin will configure a cron job to scan for directories within each shared folder's "archive" directory that have names ending with `.ready`. When these directories are identified, the `cron` job will rename them to `xxxx.archive` and set them to read-only, preventing users from adding additional files.

**Step 5: Initiate Archiving**

Admin will use a script to copy the `xxxx.archive` directory to the server hosting the tape drive and begin the archiving process to tapes.

**Step 6: Verification and Cleanup**

After the archiving job is complete, Admin's script will verify the consistency of the files backed up on the tapes with the original files. A list of these files will be placed in the `xxxx.archive` directory, and the original files in that folder will be deleted.

**Step 7: Final Note**

Admin will ensure that both the `xxxx.archive` directory and the list of archived files inside it are set to read-only for the group.

