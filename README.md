# autosqlitebackup
automysqlbackup fork for SQLite backups

automated daily backup for SQLite databases :
 - monthly backup (no cleanup)
 - weekly backup (no history)
 - daily backup (7 days history)
 
 you can only do a monthly backup if you want, see MDBNAMES option

## no one is fool enough to use sqlite databases in production
but if you do, you may need such a backup tool

## requirements

- sqlite
- mailx (but this is not really mandatory since you won't have any error mail anyway, see below)
- gzip to compress dumps (enabled by default)
- bzip2 or xz to use another compression tool (if enabled)

## installation
1. copy autosqlitebackup backup script to some location on the server hosting the SQLite database(s) you want to backup, for instance in /usr/local/sbin/
2. copy autosqlitebackup.conf file in the folder /etc/autosqlitebackup/ (you may have to create it first) and change it to fit your needs (mainly DBNAMES and MAILADDR ariables)
3. copy cron.daily_autosqlitebackup file in the folder /etc/cron.daily/autosqlitebackup (change the backup script location if needed
4. pray

## configuration

Edit /etc/autosqlitebackup/autosqlitebackup.conf to fit your needs

for instance DBNAMES for Daily/Weekly Backup e.g. "fancyname1:/var/lib/myapp/data/database.sqlite fancyname2:/var/lib/myotherapp/myotherapp.sqlite"


## warranty

absolutely none

this should send you an email when backup fails **but** since sqlite3 seems to always return 0 you probably won't have any
