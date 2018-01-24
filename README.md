Liquibase CLI
=============
- Restart the application after making changes to JPA entities.
- Check start up logs for hbm2ddl info messages.
- Run **mvn liquibase:diff** from project root to generate db.changelog-diff-${maven.build.timestamp}.xml.
- Append the above file in **db.changelog-master.xml.**
- Run **mvn liquibase:status** to view the enqueued changesets.
- Run **mvn liquibase:update** to apply the changes to the target database.
- Run **mvn liquibase:rollback -Dliquibase.rollbackCount=1** in case a rollback is required.
- Run **mvn liquibase:help -Ddetail=true** to get help on all the plugin’s commands and their arguments.


Generate first Changelog file
=============================

- Run **mvn clean resources:resources liquibase:generateChangeLog** -Dliquibase.outputChangeLogFile=output.xml