# InformixAudit

These are commands to help assist with retrieving the database version and users with administrative access to the database The commands are designed to only read data and will not modify or create data inside of the database.

## Database Version

This will show the version of the Informix database.

``` Bash
onstat -V > version.txt
```

If the above command doesn't work, use this one.

``` Bash
dbaccess -V > version.txt
```

## Administrator Users

This will show information on the users with administrative privileges to the Informix database.


To run the following command, navigate to the location of the following directories: $INFORMIXDIR/etc, $INFORMIXDIR/dbssodir, $INFORMIXDIR/aaodir.
``` Bash
ls-lg > roleSeparation.txt
```

To run the following command, navigate to the $INFORMIXDIR directory.
``` Bash
onstat -c > onconfigFile.txt
```

Run the following query from DB-Access or the application.
``` Bash
select username,usertype from sysusers > SQLprivs.txt
```