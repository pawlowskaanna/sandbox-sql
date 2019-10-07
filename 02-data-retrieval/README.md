# Data Retrieval samples for learning purpose
Sample SQL statements

:wrench: PL: Konkatenacja tekstu i danych jako nazwana kolumna  
           ENG: Concatenation of text and data as a named column

    SELECT 
        'The Job ID for the ' || JOB_TITLE || '''s' || ' job is: ' || JOB_ID AS "Job description" 
    FROM HR.JOBS;

![alt text](https://github.com/pawlowskaanna/sandbox-sql/blob/master/02-data-retrieval/images/ch02q2.PNG )

---

:wrench: PL: Obliczanie pola koła, przy uzyciu tabeli DUAL ; r=6000, pi=22/7  
         ENG: Calculating the area of a circle, using the DUAL table ; r=6000, pi=22/7
         
         
    SELECT (22/7) * (6000 * 6000 ) "Area"
    FROM SYS.dual

![alt text](https://github.com/pawlowskaanna/sandbox-sql/blob/master/02-data-retrieval/images/ch02q3.PNG )
