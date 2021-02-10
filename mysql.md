# MYSQL Cheatsheet

>Disclaimer: This cheatsheet is summarized from personal experience and other online tutorials. It should not be considered as an official reference.

## Queries
```bash
SELECT count(*) AS TOTALNUMBEROFTABLES FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_SCHEMA = 'database';          # get total number of tables from database
```

## mysqldump
```bash
mysqldump --routines --no-create-info --no-data --no-create-db --skip-opt icarasia_CRMPortal                    # dump all triggers from database
```