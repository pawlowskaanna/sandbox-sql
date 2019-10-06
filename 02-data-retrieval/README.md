# Data Retrieval samples for learning purpose
Sample SQL statements

:wrench: PL: Konkatenacja tekstu i danych jako nazwana kolumna

    SELECT 
        'The Job ID for the ' || JOB_TITLE || '''s' || ' job is: ' || JOB_ID AS "Job description" 
    FROM HR.JOBS;

![alt text](https://github.com/pawlowskaanna/sandbox-sql/blob/master/02-data-retrieval/images/ch02q2.PNG )

---

