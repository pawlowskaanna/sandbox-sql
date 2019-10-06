# Data Retrieval samples for learning purpose
Sample SQL statements

:wrench: PL: Konkatenacja tekstu i danych jako nazwana kolumna

    SELECT 
        'The Job ID for the ' || JOB_TITLE || ' job is: ' || JOB_ID AS "Job description" 
    FROM HR.JOBS;
